# Word Embedding / Word Representation Learning / Word Vectors / Word Level Modelling

# $\color{cyan}{Step1:\ Word\ Tokenization}$
Given a paragraph (corpus) you need to extract all the unique words in that corpus is what is called word tokenization or word segmentation.

# $\color{cyan}{Step2:\ Stemming,\ Lemmatization\ and\ Stopword\ Removal}$
This [video](https://www.youtube.com/watch?v=JpxCt3kvbLk) here explains stemming and lemmetization really well and for code you can refer [here](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stemming_Lemmetization.ipynb). Stopwords are just some common words like articles, prepositions, and pronouns (e.g., "the," "is," "and") that are frequently filtered out to focus on more meaningful terms. You can refer to stopwords code [here](https://github.com/khetansarvesh/NLP/blob/main/Preprocessing/Stopwords.ipynb).

# $\color{cyan}{Step3:\ Word\ Representation}$
I.e. to convert the corpus into its numerical form we convert all the words in the corpus into its numerical form first and then combine them in some way to get the numerical form of the corpus. 

Now once we have got the numerical representation of all the words present in the corpus which is a 1*n row vector, to get the numeric representation of the corpus which will also be 1*n row vector you can either sum up all these numerical representations of words present in the corpus or you can average them out or ….. Consider this as a hyperparameter.
