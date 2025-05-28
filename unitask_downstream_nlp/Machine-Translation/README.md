# Machine Translation (MT)

This folder contains a notebook which jointly trains English to French MT system containing a character level Unstacked LSTM Encoder and a character Level Unstacked LSTM Decoder


Translating a language A to language B is called monolingual machine translation system eg english to hindi.
      - There are many ways to solve MT problems but we will use similar techniques to what we used to solve [Image2Text](https://pub.towardsai.net/natural-language-generation-x2text-tasks-78641031b033#1341) Problem i.e. Deep Learning / Neural Machine Translation (NMT) just that this time we will condition the language model on another text information rather than image information.

<pre> ```python def hello(): print("Hello, world!") ``` </pre>


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
