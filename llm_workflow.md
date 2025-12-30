Workflows are systems where LLMs and tools are orchestrated through predefined static paths. There are many differnt syles of workflows possible, few prominent onces are !

# $\color{red}{1.Prompt\ Chaining\  Workflow }$
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/prompt_chaining_workflow.png">

# $\color{red}{2.Routing\  Workflow }$
Routing classifies an input and directs it to a specialized followup task. This workflow allows for separation of concerns, and building more specialized prompts. Without this workflow, optimizing for one kind of input can hurt performance on other inputs.
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/routing_workflow.png">

# $\color{red}{3.Parallization\  Workflow }$
LLMs can sometimes work simultaneously on a task and have their outputs aggregated programmatically.
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/parallization.png">

# $\color{red}{4.Orchestrator\ Workers\  Workflow }$
In the orchestrator-workers workflow, a central LLM dynamically breaks down tasks, delegates them to worker LLMs, and synthesizes their results.

<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/orchestrator_worker_workflow.png">

# $\color{red}{5.Evaluator\ Optimizer\  Workflow }$
In the evaluator-optimizer workflow, one LLM call generates a response while another provides evaluation and feedback in a loop.
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/eval_optimizer_workflow.png">

### $\color{blue}{ 5.1.\ ReAct\ (Reason\ -\ Action)\ :\ running\ tools\ in\ loop\}$
```python
<System> … </System>

<Question> Which country has a higher population density: Japan or India? </Question>

<Thought> I need to find the population and area of Japan. </Thought>
<Action>search_internet</Action>
<Action_Input>population and area of Japan</Action_Input>
<Observation> Japan has a population of 125 million and an area of 377,975 square kilometers. </Observation>

<Thought> I need to find the population and area of India. </Thought>
<Action>search_internet</Action>
<Action_Input>population and area of India</Action_Input>
<Observation> India has a population of 1.38 billion and an area of 3,287,263 square kilometers. </Observation>

<Thought> I need to calculate the population densities of Japan and India. </Thought>
<Action>calculate</Action>
<Action_Input>125 million / 377,975 and 1.38 billion / 3,287,263</Action_Input>
<Observation> Japan: 330.7 people/km²; India: 419.6 people/km². </Observation>

<Thought> India has a higher population density than Japan. </Thought>
<Action>Done</Action>
<Final_Answer> India has a higher population density (419.6 people/km²) than Japan (330.7 people/km²). </Final_Answer>
```

### $\color{blue}{5.2.\ ReAct\ (Reason\ -\ Action)\ with\ RAG\ based\ tool\ calling}\$

### $\color{blue}{5.3.\ CodeAct\}$
```python
<System> You are a Python programmer. Write code to solve tasks... </System>

<Question> What's the weather in Tokyo? </Question>

<Code>
```python\nweather = get_weather('Tokyo', 'celsius')\nprint(weather)\n```
</Code>

<Execution>
{'temperature': 22, 'condition': 'sunny'}
</Execution>

<Answer>
The weather in Tokyo is sunny at 22°C.
</Answer>
```

### $\color{blue}{5.4.\ SERA\}$
