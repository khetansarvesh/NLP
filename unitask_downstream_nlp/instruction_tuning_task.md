# $\color{yellow}{Normal\ Mode}$


### $\color{blue}{A.\ Standard\ Instruction\ Tuning}$
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

```python
<|im_start|>system
#You are a helpful assistant focused on technical topics.
<|im_end|>

<|im_start|>user
#Hi there!
<|im_end|>

<|im_start|>assistant
#Nice to meet you!
<|im_end|>

<|im_start|>user
#Can I ask a question?
<|im_end|>

<|im_start|>assistant
```

### C. Instruction Tuning with Chat + Tool Calling Template
----------------------------------------------------------
Here is an amazing [notebook](https://colab.research.google.com/#fileId=https%3A//huggingface.co/agents-course/notebooks/blob/main/bonus-unit1/bonus-unit1.ipynb) by hugging face.

```python
<|im_start|>system
'''
## Metadata

Knowledge Cutoff Date: June 2025
Today Date: 01 September 2025
Reasoning Mode: /think

## Custom Instructions

You are a helpful assistant with access to tools.

### Tools

You may call one or more functions to assist with the user query.
You are provided with function signatures within <tools></tools> XML tags:

<tools>
{'type': 'function', 'function': {'name': 'get_weather', 'description': 'Get the current weather for a location', 'parameters': {'type': 'object', 'properties': {'location': {'type': 'string', 'description': 'The city and state, e.g. San Francisco, CA'}, 'unit': {'type': 'string', 'enum': ['celsius', 'fahrenheit'], 'description': 'The temperature unit'}}, 'required': ['location']}}}
{'type': 'function', 'function': {'name': 'calculate', 'description': 'Perform mathematical calculations', 'parameters': {'type': 'object', 'properties': {'expression': {'type': 'string', 'description': 'Mathematical expression to evaluate'}}, 'required': ['expression']}}}
</tools>

For each function call, return a json object with function name and arguments within <tool_call></tool_call> XML tags:
<tool_call>
{"name": <function-name>, "arguments": <args-json-object>}
...
{"temperature": 22, "condition": "sunny", "humidity": 60}
'''
<|im_end|>





<|im_start|>assistant
'''
The weather in Paris is currently sunny with a temperature of 22°C and 60% humidity. It's a beautiful day!
'''
<|im_end|>
```


# $\color{yellow}{Reasoning\ Mode}$
Exactly same as above just that now our dataset changes slightly, we make use of reasoning dataset. This dataset consists of {question}{answer} pairs and the answer has the entire thinking / reasoning steps in it.



```python
<|im_start|>user
#What is 15 × 24?
<|im_end|>

<|im_start|>assistant

<|thinking|>
#I need to multiply 15 by 24. Let me break this down:
#15 × 24 = 15 × (20 + 4) = (15 × 20) + (15 × 4) = 300 + 60 = 360
</|thinking|>

<answer>
#15 × 24 = 360
</answer>

<|im_end|>
```
