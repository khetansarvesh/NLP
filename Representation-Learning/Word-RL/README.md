# Word Embedding / Word Representation Learning / Word Vectors / Word Level Modelling

# $\color{cyan}{Step1:\ Word\ Tokenization}$
Given a paragraph (corpus) you need to extract all the unique words in that corpus is what is called word tokenization or word segmentation. Now exacting this is not so easy because there can be many edge cases for instance
- [what're] : here should we consider this as two words "what are" or a single word "what're"
- [state-of-the-art] : here should we consider this as 4 words or just a single word?
- [San Francisco] : should we consider this as 2 word or a single word?

Above I have just listed english specific edge cases, similarly each language can have it's own specific edge cases (French / Spanish / Chinese). Refer [this](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Word-Tokenization.ipynb) code for english word tokenization. 

# $\color{cyan}{Step2:\ Stemming,\ Lemmatization\ and\ Stopword\ Removal}$
This [video](https://www.youtube.com/watch?v=JpxCt3kvbLk) here explains stemming and lemmetization really well and for code you can refer [here](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stemming_Lemmetization.ipynb). Stopwords are just some common words like articles, prepositions, and pronouns (e.g., "the," "is," "and") that are frequently filtered out to focus on more meaningful terms. You can refer to stopwords code [here](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stopwords.ipynb).

# $\color{cyan}{Step3:\ Word\ Representation}$
I.e. to convert the corpus into its numerical form we convert all the words in the corpus into its numerical form first and then combine them in some way to get the numerical form of the corpus. 

Now once we have got the numerical representation of all the words present in the corpus which is a 1*n row vector, to get the numeric representation of the corpus which will also be 1*n row vector you can either sum up all these numerical representations of words present in the corpus or you can average them out or ….. Consider this as a hyperparameter.

So how to convert words into numeric representations?? It can be one of the following : 

- Non-Modelling Way (Brute Force Approach)
  - One Hot Encoding (Gives non-contextual word embeddings)

- Modelling Way
This can be done by training a model for a task and hence using the representations generated during this task as word numeric representation. We can choose any task but if chosen the right task then downstream task accuracies will improve, hence how to choose the right task?? Any task will always fall under one of the learning types i.e. <ins> supervised </ins> / <ins> unsupervised </ins> / ...... Researchers have shown that one should always use an unsupervised learning task for generating embeddings. Unsupervised learning can be divided into <ins> Self-Supervised Learning (SSL) Task </ins>





