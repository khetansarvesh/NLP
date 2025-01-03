# ********** Similarity Search Based Tasks ********** 

### 1. Text-2-Text Retrival 


### 2. Factoid QA / Reasoning QA 
Problem Statement : You will be given a question and the answer needs to be ‘generated’ by looking into all the documents, remember ‘generated and not searched’ meaning answer given by the system would mean the same but the vocabulary and sentence framing might be different than what is found inside the documents

Solution : 
Simply use vector similarity approach i.e. create vector embedding of question and vector embedding of all the documents and then use similarity measure to find out what the answer is








# ********** Non Generative Tasks -- Natural Language Understanding (NLU) Task ********** 
- Sentence level classification problems
- Token/word level classification problems








# ********** Generative Tasks / Natural Language Generation (NLG) Tasks / Text-2-Text Tasks / Sequence-2-Sequence (Seq2Seq or S2S) Tasks **********
This is a family of tasks in which we generate new sentences using input sentences. These include tasks like
  1. Machine Translation (MT)
  2. [Text Summarization](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp/text_summarization)
  3. [Paraphrasing](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/paraphrase.png)
  4. [Machine Transliteration](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/trans.png)
  5. Dialogue Systems (Chatbots) : Earlier these were rule based Chatbots but now they are ML / DL based
  6. Text2Code Generation
  7. In fact all NLU tasks can be framed as a NLG task, for instance
     - Sentimental Analysis output will be ‘this is a positive sentiment’ rather than classification of positive and negative.
     - Similarly QA can be formed as a NLG task

