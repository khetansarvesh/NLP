# Instruction Tuning Task

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
