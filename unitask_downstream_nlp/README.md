# ********** Similarity Search Based Tasks ********** 

### 1. Text-2-Text Retrival / Information Retrieval (IR)

<ins> Problem Statement </ins> : Given an input question we need to find text document(s) which contains answers to this input question

<ins> Solution (RAG Based System) </ins> : 
1. Create vector embeddings (of both input question + text documents) and store them in a vector database (also called index)
2. Now calculate similarity (query , Doc1) , (query , Doc2), ... 
4. Perform ranking based on how similar the document is wrt the input query
5. Output top K similar documents



### 2. Factoid QA / Reasoning QA / Information Extraction (IE)
<ins> Problem Statement </ins> : Now let's say from above IR system you identified 10 documents relevant to your input query, now your task is to 'generate' an answer by looking into all these 10 documents. Remember ‘generated and not searched’ meaning answer given by the system would mean the same but the vocabulary and sentence framing might be different than what is found inside the documents

<ins> Solution </ins> : 
You can simply pass the input question and these 10 documents in an LLM to extract exact answer of the query








# ********** Non Generative Tasks -- Natural Language Understanding (NLU) Task ********** 
- Sentence level classification problems
- Token/word level classification problems (also called Sequence Learning) : Word / Token level classification problem is a problem in which you classify each word / token in the corpus as something.









# ********** Generative Tasks / Natural Language Generation (NLG) Tasks / Text2Text Tasks / Sequence2Sequence (Seq2Seq or S2S) Tasks / Sequence2Sequence Learning **********
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

