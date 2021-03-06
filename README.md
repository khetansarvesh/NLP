# NLP

# Representation Learning
Before performing any NLP Task it is important to convert natural language into its equivalent numerical form so that we can feed it into the model because computers cannot understand languages. There are numerous ways to do this and is an active research area, please refer to my notes linked below (recommended read) which has been collect by extensive literature survey of 2 months to understand some of the SOTA techniques like Word2Vec, BERT, GPT ... to do this.

Notes: https://drive.google.com/drive/folders/1xIgG-IPXLbB8Q7L7lVAspF824WkpZNbz?usp=sharing

# Natural Language Understanding (NLU) Task
There are several NLP task of which one is NLU task.This task includes sentence level classification problems or token/word level classification problems

## *Sentence Level Classification Problems*
Please refer to following link which contains notes explaining how to handle this problem and 3 notebooks

   Notes : https://drive.google.com/drive/folders/1k0DjnHjitHRpmz-HoeFuMQ1kU-V8taYw?usp=sharing
   
   Notebook1 : Sentimental Analysis of Movie Review without joint training https://colab.research.google.com/drive/1rNqEkn4k3g56oiTf1nWXiypHHWdFkHhZ?usp=sharing
   
   Notebook2 : Sentimental Analysis of Movie Review using joint training https://colab.research.google.com/drive/1y938G9UPNT20fLfAKcsIcLrcsos1_YZV?usp=sharing
   
   Notebook3 : Toxic Comment Classification Problem by fine tuning pre-trained DistilBERT Model https://drive.google.com/file/d/1ZSjKyq1hCTopg3NHivnLo0_3vi_2UO1d/view?usp=sharing
   
## *Word Level Classification Problems*
There can be numerous word level classification tasks, some of those are

### *1. POS Tagging Task*
Please refer to following link which contains notes explaining how to handle this problem and a notebook which implements a single hidden layer LSTM RNN architechture joined trained with a no hidden layer FFNN to solve the POS Tagging task.It also contains some pretrained models for POS Tagging tasks using Spacy and NLTK library

   Notes : https://drive.google.com/drive/folders/10KtNXwuBFDPgvDdOeXsl3OekBlnkJD5K?usp=sharing
   
   Notebook1 : https://drive.google.com/file/d/1Xm2VPZxqYiPP9263yZkTU2NmH462OGXH/view?usp=sharing
   
### *2. NER Task*
Please refer to following link which contains notes explaining how to handle this problem, this is exactly similar to the POS Tagging Task except the fact that POS Tagging is a 36 class classification problem which NER is just 7 class classification problem, and rest everything is exactly same.
   
   Notes : https://drive.google.com/drive/folders/1lfWgurbzchI1vUkOBjBe-rOFevO-o4Zh?usp=sharing

# Natural Language Generation (NLG) Task
There are again numerous NLG Tasks some of which are

### *1. Machine Translation (MT)*
Notes : https://drive.google.com/drive/folders/1nB1wGCp0AEvpW7jN6-5ZSC7-e-Y-It6x?usp=sharing

This folder contains a notebook which jointly trains English to French MT system containing a character level Unstacked LSTM Encoder and a character Level Unstacked LSTM Decoder

### *2. Image Captioning*
Notes : https://drive.google.com/drive/folders/1QqXHRttJEMVYgs7_4lvScFG2VcBcZ_Ho?usp=sharing
