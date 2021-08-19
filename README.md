# NLP

*Sentence Level Classification Problems*
---------------------------------------------------------------------------------------------------
1. Sentimental Analysis using LSTM

   Notebook: https://drive.google.com/file/d/1CUzJb5AEHnHCUqfAqITicivZeqa3uG52/view?usp=sharing
   
2. Spam-Mail-Detection----From-Scratch

The dataset used can be found at following link : https://drive.google.com/file/d/1u5EjHziYhUGm34y24nH3WQyJSRP_ctaH/view?usp=sharing

The code can be found here :  https://colab.research.google.com/drive/1xdPBL_t8tQgwusL0L-CFlN8IqApeZNdP?usp=sharing

The code can be divided into following parts for easy understanding.

## Importing Required Libraries
First we will be importing all the necessary libraries like pandas, numpy, regular expressions ... to perform basic operation in our code

## Data Preprocessing - Natural Language Processing (NLP)
The original dataset is in form of text which has been converted into a cross section dataset using NLP technique like tokenization i.e. remove the stop words and punctuations from the given dataset as they don’t contribute to the sentiment of the text.

## Data Learning Using Naive Bayes (NB) Algorithm 
Now after performing NLP on the textual data, textual data got converted into cross sectional data and now we can use any classification algorithm to solve this classification problem. Now since we know that Naive bayes works best for textual data hence we will be using Naive Bayes algorithm.

To understand the mathematical intuition behind the naive bayes algorithm you can refer to following link: https://drive.google.com/drive/folders/1_ECEyARYQFOIonmnc-KKYinJjZ3KQnec?usp=sharing

Laplace smoothing is performed to avoid the problem of zero frequency problem.Hence when a new message comes in, our Naive Bayes algorithm will make the classification based on the results it gets to these two equations below, where "w1" is the first word, and w1,w2, ..., wn is the entire message:

                                         P(Wi|Spam) = (N_wi|spam + alpha) / (N_spam + alpha* N_vocabulary)
                                         
Where Nwi is the frequency of a word given it is a spam mail, NSpam is the number of spam mails and Nvocabulary is no of words present in the dataset. Also alpha is the smoothening parameter whose value is set to 1 in out model.

In our model we divide the given dataset into 7 parts using the concept of ‘k-fold classification’. After all the processing the model is trained individually by each of the 7 datasets. A Numpy array is used which stores the frequency of each word given it is spam or not. This frequency is used to calculate the Bayesian probability while testing our model. Both probabilities (given a word whether a mail is spam or not) are calculated. Both the calculated probabilities are then compared and a mail is classified as spam or not based on the factor which probability is greater.

The model is tested and trained by using the 7-cross validation method. 
The results from the 7-fold classification are shown below: -

     Fold_No     True_Positive     False_Positive     Accuracy

       1             115                33              77.70%    -----------------
                                                                                  |
       2             117                25              82.39%                    |
                                                                                  |
       3             124                18              87.32%                    |
                                                                                  |       Average no of Rightly Classified Mails :-806
       4             115                27              80.99%                    |-------Average no of Wrongly classified Mails: -194
                                                                                  |       Average Accuracy: - 80.62%
       5             109                33              76.76%                    |
                                                                                  |
       6             111                31              78.17%                    |
                                                                                  |
       7             115                27              80.99%   ------------------



*Word / Token Level Classification Problems*
---------------------------------------------------------------------------------------------------
1. Name Entity Relation (NER) Tagging

   Notebook: https://colab.research.google.com/drive/1tgriQ4EWbRI746M9rtnTVrjmqGllDfUo?usp=sharing
