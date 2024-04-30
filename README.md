# NLP

# Representation Learning
Before performing any NLP Task it is important to convert natural language into its equivalent numerical form so that we can feed it into the model because computers cannot understand languages. There are numerous ways to do this and is an active research area, please refer to my notes linked below (recommended read) which has been collect by extensive literature survey of 2 months to understand some of the SOTA techniques like Word2Vec, BERT, GPT ... to do this.

Notes: https://drive.google.com/drive/folders/1Qyan1BEMC62uibJkjckfeKXTMeqJ5Vdw?usp=sharing

# Natural Language Understanding (NLU) Task
There are several NLP task of which one is NLU task.This task includes sentence level classification problems or token/word level classification problems

## *Sentence Level Classification Problems*
Notes : https://drive.google.com/drive/folders/1V4_Qm_JsFwETFtkVzfA2wlfTkLHyIq4s?usp=sharing
Codes : https://github.com/khetansarvesh/NLP/tree/main/Sentence-Level-Classification

## *Word Level Classification Problems*
There can be numerous word level classification tasks, some of those are

### *1. POS Tagging Task*
Please refer to following link which contains notes explaining how to handle this problem and a notebook which implements a single hidden layer LSTM RNN architechture joined trained with a no hidden layer FFNN to solve the POS Tagging task.It also contains some pretrained models for POS Tagging tasks using Spacy and NLTK library

   Notes : https://drive.google.com/drive/folders/1ZJKxrqJaMCu2UbwNiiKIvv71LXUWlJx4?usp=sharing
   
   Notebook1 : https://drive.google.com/file/d/1cWWydWzc3eyNSy1B4K-_uEQMOMoAqXnJ/view?usp=sharing
   
### *2. NER Task*
Please refer to following link which contains notes explaining how to handle this problem, this is exactly similar to the POS Tagging Task except the fact that POS Tagging is a 36 class classification problem which NER is just 7 class classification problem, and rest everything is exactly same.
   
   Notes : https://drive.google.com/file/d/1721ThVhU8lX-4Y3XiVOiFU8pGJSzjfk2/view?usp=sharing

# Natural Language Generation (NLG) Task
There are again numerous NLG Tasks some of which are

### *1. Machine Translation (MT)*
Notes : https://drive.google.com/drive/folders/1H7KkT7pa8_Me15xhm_Dbxw6av4V6cS-R?usp=sharing

This folder contains a notebook which jointly trains English to French MT system containing a character level Unstacked LSTM Encoder and a character Level Unstacked LSTM Decoder
