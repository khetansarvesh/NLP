# $\color{yellow}{1.\ Normal\ Mode}$


### $\color{blue}{1.A.\ Standard\ Instruction\ Tuning}$
----------------------------------------------------------
Now above we saw how to create different models for different individual tasks, for instance, we have a seperate model for POS tagging, a seperate model for Machine translation, ...

Researchers hypothesised that if we can create a single model which can do all these tasks then such a model will be able to generalize to other unseen tasks i.e. tasks that it has not seen during the training. (Well their hypothesis turned out to be correct !!)

Creation of such a model became feasible because all of these tasks NLU (pos_tagging / ner/ ...) and NLG (machine_traslation / summarization/ ...) can be seen as next token prediction task on which the foundation LLMs are trained upon.
- Sentimental Analysis output will be ‘this is a positive sentiment’ rather than classification of positive and negative.
- Similarly QA can be formed as a NLG task
  
Hence to create such a general model, we just need to finetune the base LLM on a dataset just like above. Infact, along with multiple tasks you can add multiple languages too in this dataset to make the model Multilingual !! 

### $\color{blue}{1.B.\ Instruction\ Tuning\ with\ Chat\ Template}$
----------------------------------------------------------
Now you might have interacted with applications like chat_gpt, such applications can perform different types of task but in a chat format. Hence to make such a model we need to finetuning the model via a chat like design template of the data, one of the example is shown below. Similarly the entire dataset is framed in such format

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
#Can you help me translate this to hindi : 'My name is Sarvesh Khetan and I study at Unviersity of Maryland, College Park'
<|im_end|>

<|im_start|>assistant
```
Some famous models which are trained using chat template are :
- InstructGPT / ChatGPT by openAI:- Based Model used was GPT3 and in total 30k NLP tasks were trained on this model
- Google FLANG LaMDA and LaMDA2:- Base Model used was LaMDA
- Google FLANG PALM:- Base Model used was PALM
- Google FLANG T5:- Base Model used was T5
- Google FLANG U PALM:- Base Model used was U PALM
- Google MED PALM Based Model used was FLAN PALM
- OPT-IML by Facebook
- Llama 7B | 13B | 32B | 65B by meta
- Llama2 7B | 13B| 70B by meta

### $\color{blue}{1.C.\ Instruction\ Tuning\ with\ Chat\ Template\ and\ Tool\ Calling\ Template}$
----------------------------------------------------------
Recently we have seen that models are given access to tools so that it hallucinates less and responds faster. For instance, if we ask the llm to perform calculation 2 + 4, instead of leaving this for the LLM to solve we can give the llm access to a calculator tool thus reducing the compute to process this calculation (thus also reducing the response time) and also preventing it from making errors.

Moreover, one of the biggest issue with LLM was that it did not have access to latest data and using tool call we can eliminate this drawback of the llms.

Now to finetune models such that they can call tools, we use this kind of chat_tool_template

```python
<|im_start|>system
'''
## Custom Instructions

You are a helpful assistant with access to tools.

## Tools

You may call one or more functions to assist with the user query.
You are provided with function signatures within <tools></tools> XML tags:

<tools>
{
  'type': 'function',
  'function': {
                'name': 'get_weather',
                'description': 'Get the current weather for a location',
                  'parameters': {
                                  'type': 'object',
                                  'properties': {
                                                  'location': {'type': 'string', 'description': 'The city and state, e.g. San Francisco, CA'},
                                                  'unit': {'type': 'string', 'enum': ['celsius', 'fahrenheit'],'description': 'The temperature unit'}
                                                },
                                  'required': ['location']
                                }
              }
}

{
  'type': 'function',
  'function': {
                'name': 'calculate',
                'description': 'Perform mathematical calculations',
                'parameters': {
                                'type': 'object',
                                'properties': {'expression': {'type': 'string', 'description': 'Mathematical expression to evaluate'}},
                                'required': ['expression']
                              }
              }
}
</tools>

For each function call, return a json object with function name and arguments within <tool_call></tool_call> XML tags:
<tool_call>
{"name": <function-name>, "arguments": <args-json-object>}
...
{"temperature": 22, "condition": "sunny", "humidity": 60}
'''
</tool_call>

<|im_end|>





<|im_start|>assistant
'''
The weather in Paris is currently sunny with a temperature of 22°C and 60% humidity. It's a beautiful day!
'''
<|im_end|>
```
Here is an amazing [notebook](https://colab.research.google.com/#fileId=https%3A//huggingface.co/agents-course/notebooks/blob/main/bonus-unit1/bonus-unit1.ipynb) by hugging face where we finetune an LLM to perform tool calling.


# $\color{yellow}{2.\ Reasoning\ Mode}$
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
Similarly we can have tool based reasoning template.
