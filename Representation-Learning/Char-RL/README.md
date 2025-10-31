# Character Embedding / Character Representations Learning / Character Vectors / Character Level Modelling

# $\color{cyan}{Step1:\ Character\ Tokenization}$
Given a paragraph (corpus) you need to extract all the unique characters in that corpus is what is called character tokenization or character segmentation.


# $\color{cyan}{Step2:\ Character\ Representation}$
Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on Characters

## $\color{yellow}{Non\ Neural\ Character\ Embeddings}$
  - One Hot Encoding (non contextual)

## $\color{yellow}{Neural\ Character\ Embeddings}$

### $\color{red}{Next\ Character\ Prediction\ Task}$
Models which are used to do this task are also called language models. To differentiate these from the language models seen in word embedding, we call these ‘Character Language Models’ and those ‘Words Language Models

The following algorithms give non-contextual character embeddings
- <ins> Character N Gram Modelling </ins>
- <ins> FFNN LM </ins>

The following algorithms give contextual character embeddings
- <ins> RNN LM </ins>
- <ins> BiRNN LM </ins>
- <ins> LSTM RNN LM </ins>
- <ins> BiLSTM RNN LM </ins>
- <ins> Gated RNN LM </ins>
- <ins> BiGated RNN LM </ins>
- <ins> Transformer Encoder LM </ins>
- <ins> Transformer Decoder LM </ins>
