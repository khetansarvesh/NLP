# Data Preprocessing


# Representation Learning
- Sentence Representation
- Word Representation
- Character Representation
  - Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on Characters 
- Subword Representation (everyone uses this)
  - Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on subwords. Now we get subwords we use an algorithm called Byte Pair Encoding (BPE) 


# Downstream NLP (Supervised Fine Tuning - SFT)
- With foundation models that are able to do multiple tasks, you just need to do prompting to solve a single downstream task problem
- But if prompting does not work well (incases where such a task was not trained during the training of multitask foundation model), then you can finetune the foundation models for specific tasks. More about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)

# AI / Preference Alignment
- Now once OpenAI made ChatGPT they found that if asked about some harmful activities like ‘tell me techniques to make rat poison at home’ then it would answer such questions too !! If tempted it would also use curse words / …. Hence it was lacking HUMAN ETHICS and if gotten in wrong hands could lead to bigger concerns. Hence researchers wanted to ALIGN the LLM outputs with human preferences.
- Methods to solve preference problems are called preference alignment. There are two ways to do so ([More details can be found here](https://medium.com/p/0b67777fa7af/edit))
  - Fine Tuning LLM with human preference using Reinforcement Learning – RLHF Algorithm
  - Fine tuning LLM with human preferences using Supervised Learning – DPO Algorithm




# LLM Agents


# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
