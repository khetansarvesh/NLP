# Subword Embedding / Subword Representation Learning / Subword Vectors / Subword Level Modelling

# $\color{cyan}{Step1:\ Subword\ Tokenization}$
Given a paragraph (corpus) you need to extract all the unique subwords in that corpus is what is called subword tokenization or Subword segmentation.The challenge here is to convert the given corpus made up of words to sentences made up of subwords hence you need to find the “important” subwords. 

Algorithms which can do this are called subword tokenizers and the process is called subword modeling. There are many techniques to identify what are the important subwords in the corpus, one of them is the [Byte Pair Encoding (BPE)](https://vizuara.substack.com/p/understanding-byte-pair-encoding) technique.

There are multiple libraries that have implemented BPE but the most used ones are via tiktoken and Hugging Face Transformers library. You can learn how to code BPE from scratch [here](https://github.com/rasbt/LLMs-from-scratch/tree/main/ch02/05_bpe-from-scratch).


# $\color{cyan}{Step2:\ Subword\ Representation}$
Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on subwords.

## $\color{yellow}{Non\ Neural\ Subword\ Embeddings}$
  - One Hot Encoding (non contextual)

## $\color{yellow}{Neural\ Subword\ Embeddings}$

### $\color{red}{Next\ Subword\ Prediction\ (NSP)\ Task}$
Next word prediction is a right extreme and next character prediction is the left extreme so obvious researchers came up with the idea of the intermediate that is subword. These are called subword language models. Once you have converted words into subwords, exactly as we saw in the next word prediction, just now instead of passing words as inputs you will pass subwords as inputs. We can use any of the following sequence models to solve this problem 
- <ins> N Gram Modelling </ins>
- <ins> FFN LM </ins> : Fasttext 
- <ins> RNN LM </ins>
- <ins> BiRNN LM </ins>
- <ins> LSTM RNN LM </ins>
- <ins> BiLSTM RNN LM </ins> : ELMO (Embedding from language models) - 2018
- <ins> Gated RNN LM </ins>
- <ins> BiGated RNN LM </ins>
- <ins> Transformer Encoder LM </ins>
- <ins> Transformer Decoder LM </ins> : 
  - (Generative Pretrained Transformers) GPT2 small by OpenAI
  - GPT2 Medium by OpenAI
  - GPT2 Large by OpenAI
  - GPT2 Extra Large by OpenAI
  - DistilGPT2  by HF
  - GPT3 by OpenAI
  - Chinchilla (70B params) by Google Deepmind
  - Pathways Language Model (PaLM) 8B | 62B | 540B by GOOGLE
  - OPT (open pretrained transformers) by Facebook
  - Glam by GOOGLE


### $\color{red}{Fill\ in\ the\ Blank\ Task}$
- When this problem is seen as a time series problem then we can use any of the following sequence models to solve this problem
  - RNN MLM
  - BiRNN MLM
  - LSTM RNN MLM
  - BiLSTM RNN MLM
  - Gated RNN MLM
  - BiGated RNN MLM
  - Transformer Encoder MLM
    - Bidirectional Encoder Representations from Transformers (BERT) by google
    - BERT BASE by Google (open source)
    - BERT Large by Google
    - RoBERTa by Meta (open source) - better than BERT
    - DistilBERT by HF
    - On similarly lines many folks have made their language specific BERT as follows :
      - Chinese Bert (Chinese) : same config as BERT BASE
      - FlauBERT (French)
      - CamemBERT (French)
      - BERTje (Dutch)
      - FinBERT (Finnish)
      - BERTeus (Basque)
      - AfriBERT (Afrikaans)
      - IndicBERT (Indian languages)
  - Transformer Decoder MLM 
- When this problem is seen as a data argumentation problem then we can use any of the following encoder-decoder models to solve this problem
  - Autoencoder : Now here encoder and decoder can be any model like
    - FFNN encoder => FFNN decoder
    - (Uni/Bi)directional encoder (eg: RNN/ LSTM/ transformer) => Unidirectional decoder (eg: RNN/ LSTM/ transformer)
      - BART by google : transformer encoder => transformer decoder
      - T5 by google
  - GAN
  - ...
  - Diffusion  
