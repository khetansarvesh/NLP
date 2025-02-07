# Data Preprocessing


# Representation Learning (###pretraining)
We need to represent language mathematically i.e. given a corpus you need to convert this corpus into its numerical form. This mathematical representation is called an embedding/context and the process is called representation learning. Why do this?? Because computers understand only numbers and not texts. We can do this in several ways:

### <ins> 1. Via Sentence Embedding </ins>
I.e. to convert a paragraph into its numerical form we convert all the sentences in the paragraph into its numerical form first and then combine them via some way to get the numerical form of the paragraph.

  - Bag Of Words (BOWs) : [Theory](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/BOWs.pdf) || [Code](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/BOW.ipynb)
  - Term Freq (TF) - Inverse Document Freq (IDF) : [Theory](https://www.youtube.com/watch?v=D2V1okCEsiE) || [Code](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/TFIDF.ipynb)
  - Label Encoding : [Theory](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/Label%20Encoding.pdf) || [Code](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/Label_Encoding.ipynb)
 
The problem with this type of approach is that they result in a numerical representation which consumes a lot of useless memory if we have a large corpus due to the sparse nature of the numerical representation given by them. Hence we had to come up with other techniques given below.

### <ins> 2. Via Word Embedding </ins>
I.e. to convert the corpus into its numerical form we convert all the words in the corpus into its numerical form first and then combine them in some way to get the numerical form of the corpus. 

Now once we have got the numerical representation of all the words present in the corpus which is a 1*n row vector, to get the numeric representation of the corpus which will also be 1*n row vector you can either sum up all these numerical representations of words present in the corpus or you can average them out or ….. Consider this as a hyperparameter. 

### <ins> 3. Via Character Embedding </ins>
  - Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on Characters
    
### <ins> 4. Via Subword Embedding (everyone uses this) </ins>
  - Exactly same methods as we saw in Word representation just that instead of applying those methods on words we apply those methods on subwords. Now we get subwords we use an algorithm called Byte Pair Encoding (BPE) 

- Some famous models are :
  - InstructGPT by openAI:- Based Model used was GPT3
  - [Google FLaN PALM](https://www.youtube.com/watch?v=NVITqBHqWM4&ab_channel=DataScienceGems):- Base Model used was PALM
  - Google FLaN T5:- Base Model used was T5
  - Google FLaN U PALM:- Base Model used was U PALM
  - [Google MED PALM](https://www.youtube.com/watch?v=KBVpxR3w5G8) :- Base Model used was FLAN PALM
  - [OPT-IML](https://www.youtube.com/watch?v=6YQbwZxTQX4&ab_channel=DataScienceGems) by Meta
  - Llama by Meta


# Downstream NLP (Supervised Fine Tuning - SFT) (###posttraining)
- With foundation models that are able to do multiple tasks, you just need to do [prompting](https://www.promptingguide.ai/) to solve a single downstream task problem.
- But many times prompting does not work well, this is called HALLUCINATION PROBLEM. The model would sometimes give wrong answers to prompted questions (incases where such a task was not trained during the training of multitask foundation model)
- To solve this hallucination probelm you can finetune the foundation models for specific tasks. More about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)

# AI / Preference Alignment (###posttraining)
- Now once OpenAI made ChatGPT they found that if asked about some harmful activities like ‘tell me techniques to make rat poison at home’ then it would answer such questions too !! If tempted it would also use curse words / …. Hence it was lacking HUMAN ETHICS and if gotten in wrong hands could lead to bigger concerns. Hence researchers wanted to ALIGN the LLM outputs with human preferences.
- This was called as PREFERENCE PROBLEM
- Methods to solve preference problem are called preference alignment. There are two ways to do so ([More details can be found here](https://medium.com/p/0b67777fa7af/edit))
  - Fine Tuning LLM with human preference using Reinforcement Learning – RLHF Algorithm
  - Fine tuning LLM with human preferences using Supervised Learning – DPO Algorithm

# LLM Agents


# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
