# Subword Embedding / Subword Representation Learning / Subword Vectors / Subword Level Modelling

  - Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on subwords.
  - The challenge here is to convert the given corpus made up of words to sentences made up of subwords hence you need to find the “important” subwords.
  - Algorithms which can do this are called subword tokenizers and the process is called subword modeling. There are many techniques to identify what are the important subwords in the corpus, one of them is the [Byte Pair Encoding (BPE)](https://vizuara.substack.com/p/understanding-byte-pair-encoding) technique.
 


Once we get these subwords it is exactly the same as how we got word embeddings and character embeddings.

# $\color{cyan}{Non\ Neural\ Subword\ Embeddings}$
  - One Hot Encoding (non contextual)

# $\color{cyan}{Neural\ Subword\ Embeddings}$

## $\color{yellow}{Next\ Subword\ Prediction\ (NSP)\ Task}$
Next word prediction is a right extreme and next character prediction is the left extreme so obvious researchers came up with the idea of the intermediate that is subword. These are called subword language models. Once you have converted words into subwords, exactly as we saw in the next word prediction, just now instead of passing words as inputs you will pass subwords as inputs. We can use any of the following sequence models to solve this problem 
- N Gram Modelling
- FFN LM : Fasttext
- RNN LM
- BiRNN LM
- LSTM RNN LM
- BiLSTM RNN LM : ELMO (Embedding from language models) - 2018
- Gated RNN LM
- BiGated RNN LM
- Transformer Encoder LM
- Transformer Decoder LM
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


## $\color{yellow}{Fill\ in\ the\ Blank\ Task}$
