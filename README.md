# $\color{cyan}{Text\ Preprocessing}$
Following are some text processing you must think of doing, it is not necessary to do all these, it depends on the nlp task what text processing you want to do before doing that task
- String Manipulation using [Regex](https://www.rexegg.com/regex-quickstart.html)
- Tokenization
- Stemming & [Lemmatization](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stemming_Lemmetization.ipynb)
- Removing [Stopwords](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stopwords.ipynb)










# $\color{cyan}{Representation\ Learning\  (pretraining) }$
We need to represent language mathematically i.e. given a corpus you need to convert this corpus into its numerical form. This mathematical representation is called an embedding/context and the process is called representation learning. Why do this?? Because computers understand only numbers and not texts. We can do this in several ways:
- Via [Sentence Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Sentence-RL)
- Via [Word Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Word-RL)
- Via [Character Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Char-RL)
- Via [Subword Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/SubWord-RL) (everyone uses this)








# $\color{cyan}{Downstream\ NLP\  (posttraining) }$
## $\color{yellow}{Supervised\ Fine\ Tuning\ (SFT) }$
- Non Generative (Classification) Tasks - Natural Language Understanding (NLU) Tasks
  - [Sentence level classification Tasks](https://khetansarvesh.medium.com/sentimental-analysis-using-deep-learning-3a2dee80cf77)
  - <ins> Token / Word level classification Tasks (also called Sequence Labeling/ Learning/ Tagging Task) </ins> : 
  Word / Token level classification problem is a problem in which you classify each word / token in the corpus as something. It has been observed that a Masked Language Model based base model gives better results compared to the next subword prediction based base model on NLU tasks. There can be numerous word level classification tasks, some of those are
    - [POS Tagging](https://khetansarvesh.medium.com/pos-tagging-using-deep-learning-9e8fd316eeab#5ec3)
    - [Name Entity Recognision (NER) Tagging](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/ner.md)
    - [Reading QA / Reading Comprehension](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/reading_qa.md)
    - Token Level Languauge Identification : Classifying if a token / word is hindi or english
    - Chunking
    - Word Sense Disambiguation (WSD) / Semantic Tagging
    - Parsing
    - Discourse and Coreference Resolution

- <ins> Generative Tasks / Natural Language Generation (NLG) Tasks / Text2Text Tasks / Sequence2Sequence (Seq2Seq or S2S) Tasks / Sequence2Sequence Learning </ins> : This is a family of tasks in which we generate new sentences using input sentences. It has been observed that a next subword prediction based foundation model gives better results compared to Masked Language Model based foundation model on NLG tasks. These include tasks like
  - [Machine Translation (MT)](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/Machine-Translation/README.md)
  - [Text Summarization](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/text_summarization.md)
  - [Paraphrasing](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/paraphrase.png) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  - [Machine Transliteration](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/trans.png) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  - [Dialogue Systems (Chatbots)](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/dialogue_sys.md)
  - [Text2Code Generation](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/text2code.md)

- Instruction Tuning Task: More information about this is available [here](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/instruction_tuning_task.md)







## $\color{yellow}{Reinforcement\ Learning\ Based\ Fine\ Tuning}$
- Now above we saw how to finetune a foundational LLM model for different downstream tasks using SFT but for all those tasks we can also [finetune a foundational LLM model using RL](https://khetansarvesh.medium.com/llm-fine-tuning-using-rl-for-reasoning-857f9db05ba6).
- It has been proved previously that its better to first finetune LLM on any task using SFT and then finetune on the same task using RL, it gives better outcomes. Infact, the reference
  model used while performing RL is usually the SFT model on that task. Based on all the information, now you can finally understand <ins>how to create a reasoning LLM</ins>?
  - <ins> Step 1 </ins>: Choose a base LLM and perform SFT on it using instruction tuning reasoning dataset. This reasoning dataset consists of <question> <answer> pairs and the answer has the entire thinking process it in.
  - <ins> Step 2 </ins>: Now perform RL based finetuning on this base LLM for which the reference / offline model is the above SFT finetuned model.
  - This [notebook](https://colab.research.google.com/github/unslothai/notebooks/blob/main/nb/Qwen3_(4B)-GRPO.ipynb) from UnSloth follows this exact recepie to convert Qwen3 from a non reasoning model to a reasoning model.







# $\color{cyan}{Preference\ Alignment\ (posttraining) }$
There are two methods to do this, namely, RLHF and DPO. More information about this is available [here](https://khetansarvesh.medium.com/preference-alignment-0b67777fa7af)







# $\color{cyan}{LLM\ Agents\}$
- With foundation models that are able to do multiple tasks, you just need to do [prompting](https://www.promptingguide.ai/) to solve a single downstream task problem.
- But many times prompting does not work well, this is called HALLUCINATION PROBLEM. The model would sometimes give wrong answers to prompted questions (incases where such a task was not trained during the training of multitask foundation model)
- To solve this hallucination probelm you can finetune the foundation models for specific tasks.
-  More about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)


There are many good frameworks but some of the good ones are Langraph and Autogen (supports communication between llms)
- [ReACT](https://arxiv.org/pdf/2210.03629) Paper
- [Reflection](https://proceedings.neurips.cc/paper_files/paper/2023/file/1b44b878bb782e6954cd888628510e90-Paper-Conference.pdf) Paper







# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
