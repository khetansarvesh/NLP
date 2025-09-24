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
a. Non Generative (Classification) Tasks - Natural Language Understanding (NLU) Tasks
- [Sentence level classification Tasks](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp/Sentence-Level-Classification)
- [Token/word level classification Tasks](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp/Word-Level-Classification) (also called Sequence Learning)

b. Generative\ Tasks\ /\ Natural\ Language\ Generation\ (NLG)\ Tasks\ /\ Text2Text\ Tasks\ /\ Sequence2Sequence\ (Seq2Seq\ or\ S2S)\ Tasks\ /\ Sequence2Sequence\ Learning
This is a family of tasks in which we generate new sentences using input sentences. It has been observed that a next subword prediction based foundation model gives better results compared to Masked Language Model based foundation model on NLG tasks. These include tasks like
  1. [Machine Translation (MT)](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/Machine-Translation/README.md) : 
  2. [Text Summarization](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp/text_summarization) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  3. [Paraphrasing](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/paraphrase.png) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  4. [Machine Transliteration](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/trans.png) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  5. Dialogue Systems (Chatbots) : Earlier these were rule based Chatbots but now they are ML / DL based. Following are few famous models finetuned for Chatbot Tasks
      - ChatGPT / GPT3.5
      - CLaude
      - Dolly 2.0 by Databricks
      - Alpaca-7B | 13B Model by stanford : Fine tuned on llama-7B | 13B respectively
      - Vicuna 7B | 13B Model : Fine tuned on llama-7B | 13B respectively
      - Lambda 2 Chat 7B | 13B | 70B : Fine Tuned on Lambda2
  6. Text2Code Generation : Following are few famous models finetuned for Text2Code Generation Tasks
      - CodeWhisper
      - CodeX / Github Copilot : Fine tuned on GPT3 using publicly available code on github
      - CodeBERT
      - PyMT5
  7. In fact all NLU tasks can be framed as a NLG task, for instance
     - Sentimental Analysis output will be ‘this is a positive sentiment’ rather than classification of positive and negative.
     - Similarly QA can be formed as a NLG task



 More about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)



## $\color{yellow}{Reinforcement\ Learning\ Based\ Fine\ Tuning}$
- Now above we saw how to finetune a foundational LLM model for different downstream tasks using SFT but for all those tasks we can also [finetune a foundational LLM model using RL](https://khetansarvesh.medium.com/llm-fine-tuning-using-rl-for-reasoning-857f9db05ba6).
- It has been proved previously that its better to first finetune LLM on any task using SFT and then finetune on the same task using RL, it gives better outcomes.









# $\color{cyan}{Pposttraining}$
- AI / Preference Alignment : More information available in this [medium](https://khetansarvesh.medium.com/preference-alignment-0b67777fa7af) article.
- Tool / Function Calling Alignment : Now we finetune the LLM so that it can do tool / function calling, more on this [here](https://huggingface.co/learn/agents-course/en/bonus-unit1/introduction).







# $\color{cyan}{LLM\ Agents\}$
- With foundation models that are able to do multiple tasks, you just need to do [prompting](https://www.promptingguide.ai/) to solve a single downstream task problem.
- But many times prompting does not work well, this is called HALLUCINATION PROBLEM. The model would sometimes give wrong answers to prompted questions (incases where such a task was not trained during the training of multitask foundation model)
- To solve this hallucination probelm you can finetune the foundation models for specific tasks.


There are many good frameworks but some of the good ones are Langraph and Autogen (supports communication between llms)
- [ReACT](https://arxiv.org/pdf/2210.03629) Paper
- [Reflection](https://proceedings.neurips.cc/paper_files/paper/2023/file/1b44b878bb782e6954cd888628510e90-Paper-Conference.pdf) Paper







# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
