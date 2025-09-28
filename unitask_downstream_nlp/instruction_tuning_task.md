# $\color{yellow}{Normal\ Mode}$


### A. Standard Instruction Tuning
----------------------------------------------------------
Researchers thought that if we can finetune a base LLM so that it can perform multiple tasks / instructions then it will be able to generalize to other tasks that it has not seen during the training.(Well their hypothesis turned out to be correct !!). Now whatever NLG tasks (eg MT, text summarization, paraphrasing, ...) that we have seen can be framed as a next token prediction task. 

In fact all NLU tasks can be framed as a NLG task, for instance
- Sentimental Analysis output will be ‘this is a positive sentiment’ rather than classification of positive and negative.
- Similarly QA can be formed as a NLG task

Along with multiple tasks you can add multiple languages too here to make the model Multilingual too !! Hence for fine-tuning, the entire model architecture remains the same just that in the dataset you include multiple tasks in multiple languages !!

Some famous models are :
- InstructGPT / ChatGPT by openAI:- Based Model used was GPT3 and in total 30k NLP tasks were trained on this model
- Google FLANG LaMDA and LaMDA2:- Base Model used was LaMDA
- Google FLANG PALM:- Base Model used was PALM
- Google FLANG T5:- Base Model used was T5
- Google FLANG U PALM:- Base Model used was U PALM
- Google MED PALM Based Model used was FLAN PALM
- OPT-IML by Facebook
- Llama 7B | 13B | 32B | 65B by meta
- Llama2 7B | 13B| 70B by meta

### B. Instruction Tuning with Chat Template
----------------------------------------------------------

# My Awesome Python Project

This project demonstrates a simple Python script.

```python
<|im_start|>system
You are a helpful assistant focused on technical topics.
<|im_end|>

<|im_start|>user
Hi there!
<|im_end|>

<|im_start|>assistant
Nice to meet you!
<|im_end|>

<|im_start|>user
Can I ask a question?
<|im_end|>

<|im_start|>assistant
```

### C. Instruction Tuning with Chat + Tool Calling Template
----------------------------------------------------------
Here is an amazing [notebook](https://colab.research.google.com/#fileId=https%3A//huggingface.co/agents-course/notebooks/blob/main/bonus-unit1/bonus-unit1.ipynb) by hugging face.

# $\color{yellow}{Reasoning\ Mode}$
Exactly same as above just that now our dataset changes slightly, we make use of reasoning dataset. This dataset consists of {question}{answer} pairs and the answer has the entire thinking / reasoning steps in it.
