# 1. <ins> Text-2-Text Retrival / Information Retrieval (IR) </ins>

<ins> Problem Statement </ins> : 
   - Given an input question we need to find text document(s) which contains answers to this input question

<ins> Solution (RAG Based System) </ins> : 
   - Divide the text documents into chunks. There are many ways to do chunking, which method to choose depends on what problem statement is at hand.
      - Sentence Level Chunking
      - Paragraph Level Chunking
      - Sliding Window Based Chunking : in about two methods you can get chunk of different sizes since sentences / paragraphs can be of different sizes but here in this method you get all the chunks of same size cause you set a hyperparamter 'chunk_size' in this which determines the window of the chunk.
      - Prepositional Chunking
      - Structured Chunking
         - Say you want to chunk codes then you can spilt them based on class / functions. Thus each chunk will be of different size.
         - Say you want to chunk HTML pages then you can chunk them using H1 tags / H2 tags / Div tags.
      - [Contextual Chunking](https://www.youtube.com/watch?v=OHh_SByRYmQ)
   - Create vector embeddings (of both input question + text documents) and store them in a vector database (also called index). Choosing a right embedding model is crutial.
   - Now calculate similarity (query , Doc1) , (query , Doc2), ... 
   - Perform ranking based on how similar the document is wrt the input query. But instead of similarity nowadays people are using rerankers like [Jina AI](https://jina.ai/news/jina-reranker-v3-0-6b-listwise-reranker-for-sota-multilingual-retrieval/). Here is [why](https://www.linkedin.com/posts/anshuizme_chatgpt-rag-ai-activity-7380217740675993600-pVVp?utm_source=share&utm_medium=member_desktop&rcm=ACoAACiYXQ0B7fczwMR-uxnuOJaiYRS4N5_AkqA) rerankers are important.
   - Output top K similar documents
   - You can improve this system by using techniques like
      - 0 shot prompting / Learning
      - 1 shot prompting / learning
      - Few shot Prompting / Learning
      - Dynamic Few Shots prompting / Learning


# 2. <ins> Factoid QA / Reasoning QA / Information Extraction (IE) </ins>
<ins> Problem Statement </ins> : 
   - Now let's say from above IR system you identified 10 documents relevant to your input query, now your task is to 'generate' an answer by looking into all these 10 documents. Remember ‘generated and not searched’ meaning answer given by the system would mean the same but the vocabulary and sentence framing might be different than what is found inside the documents

<ins> Solution </ins> : 
   - You can simply pass the input question and these 10 documents in an LLM to extract exact answer of the query
