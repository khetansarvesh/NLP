# Subword Embedding / Subword Representation Learning / Subword Vectors / Subword Level Modelling

  - Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on subwords.
  - The challenge here is to convert the given corpus made up of words to sentences made up of subwords hence you need to find the “important” subwords.
  - Algorithms which can do this are called subword tokenizers and the process is called subword modeling. There are many techniques to identify what are the important subwords in the corpus, one of them is the [Byte Pair Encoding (BPE)](https://vizuara.substack.com/p/understanding-byte-pair-encoding) technique.
 


Once we get these subwords it is exactly the same as how we got word embeddings and character embeddings.

- Non Neural SubWord Embeddings
  - One Hot Encoding (non contextual)

- Neural Subword Embeddings
  - Next Subword Prediction (NSP) Task i.e. Predict SW(t) | SW(t-1), SW(t-2), ...
  - Fill in the Blank Task i.e. Predict SW(t) | SW(t-1),SW(t-2).... , SW(t+1),SW(t+2) …… 
