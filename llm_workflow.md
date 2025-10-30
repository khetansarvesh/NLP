# Prompt Chaining Workflow
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/prompt_chaining_workflow.png">

# Routing Workflow
Routing classifies an input and directs it to a specialized followup task. This workflow allows for separation of concerns, and building more specialized prompts. Without this workflow, optimizing for one kind of input can hurt performance on other inputs.
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/routing_workflow.png">

# Parallization Workflow
LLMs can sometimes work simultaneously on a task and have their outputs aggregated programmatically.
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/parallization.png">

# Orchestrator Workers Workflow
In the orchestrator-workers workflow, a central LLM dynamically breaks down tasks, delegates them to worker LLMs, and synthesizes their results.

<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/orchestrator_worker_workflow.png">

# Evaluator Optimizer Workflow
In the evaluator-optimizer workflow, one LLM call generates a response while another provides evaluation and feedback in a loop.
<img width=800 src="https://github.com/khetansarvesh/NLP/blob/main/imgs/eval_optimizer_workflow.png">
