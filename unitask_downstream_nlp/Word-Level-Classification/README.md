# *Token / Word Level Classification Problems (also called Sequence Labeling/ Learning/ Tagging Task)*
Word / Token level classification problem is a problem in which you classify each word / token in the corpus as something.

It has been observed that a Masked Language Model based base model gives better results compared to the next subword prediction based base model on NLU tasks. 

There can be numerous word level classification tasks, some of those are

## *1. Parts of Speech (POS) Tagging Task*
a notebook which implements a single hidden layer LSTM RNN architechture joined trained with a no hidden layer FFNN to solve the POS Tagging task.It also contains some pretrained models for POS Tagging tasks using Spacy and NLTK library

      
## *2. Name Entity Recognition (NER) Task*
this is exactly similar to the POS Tagging Task except the fact that POS Tagging is a 36 class classification problem which NER is just 7 class classification problem, and rest everything is exactly same.
   

## *3. Chunking*
To do chunking you can use HMM seen in POS tagging. Chunks are identified using POS tags and their dependencies.
- [InContext Learning](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/Word-Level-Classification/Chunking.ipynb)
- FineTuning
- Joint Training






