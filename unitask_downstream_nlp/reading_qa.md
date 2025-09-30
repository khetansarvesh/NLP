# Reading Question Answering System

### $\color{cyan}{Task\ Definition}$
- You are given a paragraph and a question, now your system need to find an answer from the paragraph.
- Note : You are supposed to pick the answer from the paragraph and not generate the answer. Hence your system should search and copy paste the exact answer found in the paragraph.
- Below image describes this task perfectly !!
<img align='center' alt="reading_qa" width=800 src="https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/reading_qa_task.png">


### $\color{cyan}{Dataset}$
Some standard dataset for this task are 
- Stanford Question Answering Dataset (SQuAD) -- V1.1
    - It contains 107,785 question-answer pairs on 536 articles and it does not provide a list of answer choices for each question. The model must select the answer from all possible spans in the passage, thus needing to cope with a fairly large number of candidates.
- [SQuAD -- V2.0](https://rajpurkar.github.io/SQuAD-explorer/)
    - Problem with SQuAD 1.1 dataset is that it’s guaranteed that the answer exists in the context document.
    - To address this weakness SQuAD 2.0 was released. SQuAD 2.0 combines existing SQuAD data with over 50,000 unanswerable questions written adversarially by crowd workers to look similar to answerable ones.
- XQuAD
    - Multilingual dataset.
    - This is a subset of SQuAD translated into 10 different languages by professional translators.





### $\color{cyan}{Solution}$
If you think carefully this is just like POS tagging task just that instead of 36 class classification, it is not just a 2 class classification problem.
- {START} : denotes the answer starting of the passage
- {END} : denotes the answer ending in the passage

Following is a [code](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/Word-Level-Classification/Reading_QA.ipynb) where we finetune distilBERT for the above task.
