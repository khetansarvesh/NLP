# 1. <ins> Text-2-Text Retrival / Information Retrieval (IR) </ins>

<ins> Problem Statement </ins> : 
   - Given an input question we need to find text document(s) which contains answers to this input question

<ins> Solution (RAG Based System) </ins> : 
   - Divide the text documents into chunks. There are many ways to do chunking, which method to choose depends on what problem statement is at hand.
   - Create vector embeddings (of both input question + text documents) and store them in a vector database (also called index). Choosing a right embedding model is crutial.
   - Now calculate similarity (query , Doc1) , (query , Doc2), ... 
   - Perform ranking based on how similar the document is wrt the input query. But instead of similarity nowadays people are using rerankers like [Jina AI](https://jina.ai/news/jina-reranker-v3-0-6b-listwise-reranker-for-sota-multilingual-retrieval/). Here is [why](https://www.linkedin.com/posts/anshuizme_chatgpt-rag-ai-activity-7380217740675993600-pVVp?utm_source=share&utm_medium=member_desktop&rcm=ACoAACiYXQ0B7fczwMR-uxnuOJaiYRS4N5_AkqA) rerankers are important.
   - Output top K similar documents



# 2. <ins> Factoid QA / Reasoning QA / Information Extraction (IE) </ins>
<ins> Problem Statement </ins> : 
   - Now let's say from above IR system you identified 10 documents relevant to your input query, now your task is to 'generate' an answer by looking into all these 10 documents. Remember ‘generated and not searched’ meaning answer given by the system would mean the same but the vocabulary and sentence framing might be different than what is found inside the documents

<ins> Solution </ins> : 
   - You can simply pass the input question and these 10 documents in an LLM to extract exact answer of the query

