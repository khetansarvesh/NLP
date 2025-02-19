# Text Preprocessing
Following are some text processing you must think of doing, it is not necessary to do all these, it depends on the nlp task what text processing you want to do before doing that task
- String Manipulation using [Regex](https://www.rexegg.com/regex-quickstart.html)
- Tokenization
- Stemming & [Lemmatization](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stemming_Lemmetization.ipynb)
- Removing [Stopwords](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stopwords.ipynb)











# Representation Learning (###pretraining)
We need to represent language mathematically i.e. given a corpus you need to convert this corpus into its numerical form. This mathematical representation is called an embedding/context and the process is called representation learning. Why do this?? Because computers understand only numbers and not texts. We can do this in several ways:
- Via [Sentence Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Sentence-RL)
- Via [Word Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Word-RL)
- Via [Character Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Char-RL)
- Via [Subword Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/SubWord-RL) (everyone uses this)









# Downstream NLP (Supervised Fine Tuning - SFT) (###posttraining)
- With foundation models that are able to do multiple tasks, you just need to do [prompting](https://www.promptingguide.ai/) to solve a single downstream task problem.
- But many times prompting does not work well, this is called HALLUCINATION PROBLEM. The model would sometimes give wrong answers to prompted questions (incases where such a task was not trained during the training of multitask foundation model)
- To solve this hallucination probelm you can finetune the foundation models for specific tasks. More about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)









# AI / Preference Alignment (###posttraining)
- Now once OpenAI made ChatGPT they found that if asked about some harmful activities like ‘tell me techniques to make rat poison at home’ then it would answer such questions too !! If tempted it would also use curse words / …. Hence it was lacking HUMAN ETHICS and if gotten in wrong hands could lead to bigger concerns. Hence researchers wanted to ALIGN the LLM outputs with human preferences.
- This was called as PREFERENCE PROBLEM
- Methods to solve preference problem are called preference alignment. There are two ways to do so
  - Fine Tuning LLM with human preference using Reinforcement Learning – RLHF Algorithm
  - Fine tuning LLM with human preferences using Supervised Learning – DPO Algorithm
- More information available [here](https://khetansarvesh.medium.com/preference-alignment-0b67777fa7af)








# LLM Agents











# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
