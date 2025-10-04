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



Some famous models are :
  - InstructGPT by openAI:- Based Model used was GPT3
  - [Google FLaN PALM](https://www.youtube.com/watch?v=NVITqBHqWM4&ab_channel=DataScienceGems):- Base Model used was PALM
  - Google FLaN T5:- Base Model used was T5
  - Google FLaN U PALM:- Base Model used was U PALM
  - [Google MED PALM](https://www.youtube.com/watch?v=KBVpxR3w5G8) :- Base Model used was FLAN PALM
  - [OPT-IML](https://www.youtube.com/watch?v=6YQbwZxTQX4&ab_channel=DataScienceGems) by Meta
  - Llama by Meta
