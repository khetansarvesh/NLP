# Machine Translation (MT)

This folder contains a notebook which jointly trains English to French MT system containing a character level Unstacked LSTM Encoder and a character Level Unstacked LSTM Decoder


Translating a language A to language B is called monolingual machine translation system eg english to hindi.
      - There are many ways to solve MT problems but we will use similar techniques to what we used to solve [Image2Text](https://pub.towardsai.net/natural-language-generation-x2text-tasks-78641031b033#1341) Problem i.e. Deep Learning / Neural Machine Translation (NMT) just that this time we will condition the language model on another text information rather than image information.









<pre> ```python
class Encoder(nn.Module):

    def __init__(self, input_size):
        super(Encoder, self).__init__()
        self.embedding = nn.Embedding(input_size, 300)
        self.rnn = nn.LSTM(300, 1024, 1, bidirectional=True)
        self.fc_hidden = nn.Linear(1024 * 2, 1024)
        self.fc_cell = nn.Linear(1024 * 2, 1024)

    def forward(self, x):

        embedding = self.embedding(x)
        encoder_states, (hidden, cell) = self.rnn(embedding)

        # Use forward, backward cells and hidden through a linear layer
        # so that it can be input to the decoder which is not bidirectional
        # Also using index slicing ([idx:idx+1]) to keep the dimension
        hidden = self.fc_hidden(torch.cat((hidden[0:1], hidden[1:2]), dim=2))
        cell = self.fc_cell(torch.cat((cell[0:1], cell[1:2]), dim=2))

        return encoder_states, hidden, cell


class Decoder(nn.Module):

    def __init__(self, input_size, output_size):
        super(Decoder, self).__init__()
        self.embedding = nn.Embedding(input_size, 300)
        self.rnn = nn.LSTM(1024 * 2 + 300, 1024, 1)
        self.energy = nn.Linear(1024 * 3, 1)
        self.fc = nn.Linear(1024, output_size)
        self.softmax = nn.Softmax(dim=0)
        self.relu = nn.ReLU()

    def forward(self, x, encoder_states, hidden, cell):
        x = x.unsqueeze(0)
        embedding = self.embedding(x)
        sequence_length = encoder_states.shape[0]
        h_reshaped = hidden.repeat(sequence_length, 1, 1)
        energy = self.relu(self.energy(torch.cat((h_reshaped, encoder_states), dim=2)))

        attention = self.softmax(energy)

        # attention: (seq_length, N, 1), snk
        # encoder_states: (seq_length, N, hidden_size*2), snl
        # we want context_vector: (1, N, hidden_size*2), i.e knl
        context_vector = torch.einsum("snk,snl->knl", attention, encoder_states)

        rnn_input = torch.cat((context_vector, embedding), dim=2)

        outputs, (hidden, cell) = self.rnn(rnn_input, (hidden, cell))

        predictions = self.fc(outputs).squeeze(0)

        return predictions, hidden, cell


class Seq2Seq(nn.Module):
    def __init__(self, encoder, decoder):
        super(Seq2Seq, self).__init__()
        self.encoder = encoder
        self.decoder = decoder

    def forward(self, source, target, teacher_force_ratio=0.5):
        batch_size = source.shape[1]
        target_len = target.shape[0]
        target_vocab_size = len(english.vocab)

        outputs = torch.zeros(target_len, batch_size, target_vocab_size).to(device)
        encoder_states, hidden, cell = self.encoder(source)

        # First input will be <SOS> token
        x = target[0]

        for t in range(1, target_len):
            # At every time step use encoder_states and update hidden, cell
            output, hidden, cell = self.decoder(x, encoder_states, hidden, cell)

            # Store prediction for current time step
            outputs[t] = output

            # Get the best word the Decoder predicted (index in the vocabulary)
            best_guess = output.argmax(1)

            # With probability of teacher_force_ratio we take the actual next word
            # otherwise we take the word that the Decoder predicted it to be.
            # Teacher Forcing is used so that the model gets used to seeing
            # similar inputs at training and testing time, if teacher forcing is 1
            # then inputs at test time might be completely different than what the
            # network is used to. This was a long comment.
            x = target[t] if random.random() < teacher_force_ratio else best_guess

        return outputs
      
      ``` </pre>








      











<pre> ```python
      class Transformer(nn.Module):
      
          def __init__( self, src_vocab_size, trg_vocab_size, src_pad_idx, max_len, device):
              super(Transformer, self).__init__()
              self.src_word_embedding = nn.Embedding(src_vocab_size, 512)
              self.src_position_embedding = nn.Embedding(max_len, 512)
              self.trg_word_embedding = nn.Embedding(trg_vocab_size, 512)
              self.trg_position_embedding = nn.Embedding(max_len, 512)
              self.device = device
              self.transformer = nn.Transformer( 512, 8, 3, 3, 4, 0.1)
              self.fc_out = nn.Linear(512, trg_vocab_size)
              self.src_pad_idx = src_pad_idx
      
          def forward(self, src, trg):
              src_seq_length, N = src.shape
              trg_seq_length, N = trg.shape
              src_positions = torch.arange(0, src_seq_length).unsqueeze(1).expand(src_seq_length, N).to(self.device)
              trg_positions = torch.arange(0, trg_seq_length).unsqueeze(1).expand(trg_seq_length, N).to(self.device)
              embed_src = self.src_word_embedding(src) + self.src_position_embedding(src_positions)
              embed_trg = self.trg_word_embedding(trg) + self.trg_position_embedding(trg_positions)
              src_padding_mask = (src.transpose(0, 1) == self.src_pad_idx).to(self.device)
              trg_mask = self.transformer.generate_square_subsequent_mask(trg_seq_length).to(self.device)
              out = self.transformer( embed_src, embed_trg, src_key_padding_mask=src_padding_mask, tgt_mask=trg_mask)
              out = self.fc_out(out)
              return out
      
model = Transformer( len(german.vocab), len(english.vocab), english.vocab.stoi["<pad>"], 100, device,).to(device)
      
      ``` </pre>
