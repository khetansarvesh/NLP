# Sentence Embedding / Sentence Representation Learning / Sentence Vectors / Sentence Level Modelling

Here we convert a paragraph into its numerical form we convert all the sentences in the paragraph into its numerical form first and then combine them via some way to get the numerical form of the paragraph.

  - Bag Of Words (BOWs) : [Theory](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/BOWs.pdf) || [Code](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/BOW.ipynb)
  - Term Freq (TF) - Inverse Document Freq (IDF) : [Theory](https://www.youtube.com/watch?v=D2V1okCEsiE) || [Code](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/TFIDF.ipynb)
  - Label Encoding : [Theory](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/Label%20Encoding.pdf) || [Code](https://github.com/khetansarvesh/NLP/blob/main/Representation-Learning/Sentence-RL/Label_Encoding.ipynb)
 
The problem with this type of approach is that they result in a numerical representation which consumes a lot of useless memory if we have a large corpus due to the sparse nature of the numerical representation given by them. Hence we had to come up with other techniques given below.
