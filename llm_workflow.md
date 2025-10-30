# Prompt Chaining Workflow

# Routing Workflow
Routing classifies an input and directs it to a specialized followup task. This workflow allows for separation of concerns, and building more specialized prompts. Without this workflow, optimizing for one kind of input can hurt performance on other inputs.

# Parallization Workflow
LLMs can sometimes work simultaneously on a task and have their outputs aggregated programmatically.

# Orchestrator Workers Workflow
In the orchestrator-workers workflow, a central LLM dynamically breaks down tasks, delegates them to worker LLMs, and synthesizes their results.

# Evaluator Optimizer Workflow
In the evaluator-optimizer workflow, one LLM call generates a response while another provides evaluation and feedback in a loop.
