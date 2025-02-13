# *Word Level Classification Problems*


Word / Token level classification problem is a problem in which you classify each word / token in the corpus as something.

It has been observed that a Masked Language Model based base model gives better results compared to the next subword prediction based base model on NLU tasks. 

There can be numerous word level classification tasks, some of those are

## *1. POS Tagging Task*
Please refer to following link which contains notes explaining how to handle this problem and a notebook which implements a single hidden layer LSTM RNN architechture joined trained with a no hidden layer FFNN to solve the POS Tagging task.It also contains some pretrained models for POS Tagging tasks using Spacy and NLTK library

   Notes : https://drive.google.com/drive/folders/1ZJKxrqJaMCu2UbwNiiKIvv71LXUWlJx4?usp=sharing
      
## *2. NER Task*
Please refer to following link which contains notes explaining how to handle this problem, this is exactly similar to the POS Tagging Task except the fact that POS Tagging is a 36 class classification problem which NER is just 7 class classification problem, and rest everything is exactly same.
   
   Notes : https://drive.google.com/file/d/1721ThVhU8lX-4Y3XiVOiFU8pGJSzjfk2/view?usp=sharing



Token / Word Level Classification Tasks (also called Sequence Labeling/ Learning/ Tagging Task)
Parts of Speech (POS) Tagging
Name Entity Recognition (NER)
Chunking
Word Sense Disambiguation (WSD) / Semantic Tagging
Parsing
Discourse and Coreference Resolution …
