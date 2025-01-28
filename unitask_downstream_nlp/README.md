# $\color{yellow}{Similarity\ Search\ Based\ Tasks\ }$
### 1. <ins> Text-2-Text Retrival / Information Retrieval (IR) </ins>

<ins> Problem Statement </ins> : 
   - Given an input question we need to find text document(s) which contains answers to this input question

<ins> Solution (RAG Based System) </ins> : 
   - Create vector embeddings (of both input question + text documents) and store them in a vector database (also called index)
   - Now calculate similarity (query , Doc1) , (query , Doc2), ... 
   - Perform ranking based on how similar the document is wrt the input query
   - Output top K similar documents



### 2. <ins> Factoid QA / Reasoning QA / Information Extraction (IE) </ins>
<ins> Problem Statement </ins> : 
   - Now let's say from above IR system you identified 10 documents relevant to your input query, now your task is to 'generate' an answer by looking into all these 10 documents. Remember ‘generated and not searched’ meaning answer given by the system would mean the same but the vocabulary and sentence framing might be different than what is found inside the documents

<ins> Solution </ins> : 
   - You can simply pass the input question and these 10 documents in an LLM to extract exact answer of the query






# $\color{yellow}{Non\ Generative\ Based\ Tasks\ --\ Natural\ Language\ Understanding\ (NLU)\ Tasks\ }$
### 1. <ins> Classification Tasks </ins> : 
- [Sentence level classification Tasks](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp/Sentence-Level-Classification)
- [Token/word level classification Tasks](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp/Word-Level-Classification) (also called Sequence Learning) 

### 2. <ins> Natural Language Inference (NLI) Tasks </ins> :
- [Recognizing Textual Entailment](https://aclweb.org/aclwiki/Recognizing_Textual_Entailment) (RTE) : Determine if a sentence entails a given hypothesis or not.
- [Multi-Genre Natural Language Inference](https://arxiv.org/abs/1704.05426) (MNLI) : Determines if a sentence entails, contradicts or is unrelated to a given hypothesis. (This dataset has two versions, one with the validation and test set coming from the same distribution, another called mismatched where the validation and test use out-of-domain data.)
- [Winograd Natural Language Inference](https://cs.nyu.edu/~davise/papers/WinogradSchemas/WS.html) (WNLI) : Determine if a sentence with an anonymous pronoun and a sentence with this pronoun replaced are entailed or not. (This dataset is built from the Winograd Schema Challenge dataset.)
- [Question-answering Natural Language Inference](https://rajpurkar.github.io/SQuAD-explorer/) (QNLI) : Determines if the answer to a question is in the second sentence or not. (This dataset is built from the SQuAD dataset.)









# $\color{yellow}{  Generative\ Tasks\ /\ Natural\ Language\ Generation\ (NLG)\ Tasks\ /\ Text2Text\ Tasks\ /\ Sequence2Sequence\ (Seq2Seq\ or\ S2S)\ Tasks\ /\ Sequence2Sequence\ Learning\ }$
This is a family of tasks in which we generate new sentences using input sentences. These include tasks like
  1. Machine Translation (MT)
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

