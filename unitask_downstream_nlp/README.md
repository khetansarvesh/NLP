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
