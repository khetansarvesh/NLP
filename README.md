# $\color{cyan}{Representation\ Learning\  (pretraining) }$
We need to represent language mathematically i.e. given a corpus you need to convert this corpus into its numerical form. This mathematical representation is called an embedding/context and the process is called representation learning. Why do this?? Because computers understand only numbers and not texts. We can do this in several ways:
- Via [Sentence Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Sentence-RL)
- Via [Word Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Word-RL)
- Via [Character Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/Char-RL)
- Via [Subword (or WordPieces) (or Token) Embedding](https://github.com/khetansarvesh/NLP/tree/main/Representation-Learning/SubWord-RL) (everyone uses this)

So since we have so many methods to convert our corpus into numerical representation then which one should we use?? It really depends on the data that you are trying to convert 
- if it is social media data then maybe character embedding will work better
- if your language is Chinese then maybe word embedding will work really really badly because in the Chinese language, there is no gap between words so identifying words is a big challenge hence in the Chinese language character embedding works really well and even subword embedding works really well
- In languages like French and Arabic, though there are spaces but if say we have two words in English “so said” then it is just one word in these languages, hence word embedding might not work well with these languages







# $\color{cyan}{Downstream\ NLP\  (posttraining) }$
## $\color{yellow}{A.\ Supervised\ Fine\ Tuning\ (SFT) }$
- Non Generative (Classification) Tasks - Natural Language Understanding (NLU) Tasks
  - [Sentence level classification Tasks](https://khetansarvesh.medium.com/sentimental-analysis-using-deep-learning-3a2dee80cf77)
  - <ins> Token / Word level classification Tasks (also called Sequence Labeling/ Learning/ Tagging Task) </ins> : 
  Word / Token level classification problem is a problem in which you classify each word / token in the corpus as something. It has been observed that a Masked Language Model based base model gives better results compared to the next subword prediction based base model on NLU tasks. There can be numerous word level classification tasks, some of those are
    - [POS Tagging](https://khetansarvesh.medium.com/pos-tagging-using-deep-learning-9e8fd316eeab#5ec3)
    - [Name Entity Recognision (NER) Tagging](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/ner.md)
    - [Reading QA / Reading Comprehension](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/reading_qa.md)
    - Token Level Languauge Identification : Classifying if a token / word is hindi or english
    - Chunking
    - Word Sense Disambiguation (WSD) / Semantic Tagging
    - Parsing
    - Discourse and Coreference Resolution

- <ins> Generative Tasks / Natural Language Generation (NLG) Tasks / Text2Text Tasks / Sequence2Sequence (Seq2Seq or S2S) Tasks / Sequence2Sequence Learning </ins> : This is a family of tasks in which we generate new sentences using input sentences. It has been observed that a next subword prediction based foundation model gives better results compared to Masked Language Model based foundation model on NLG tasks. These include tasks like
  - [Machine Translation (MT)](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/Machine-Translation/README.md)
  - [Text Summarization](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/text_summarization.md)
  - [Paraphrasing](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/paraphrase.png) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  - [Machine Transliteration](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/trans.png) : Architecture similar to what we used in MT can be used here, just change the dataset!!
  - [Text2Code Generation](https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/text2code.md)

- [Instruction Tuning Task](https://khetansarvesh.medium.com/instruction-tuning-4a75fd4e5149?postPublishedType=initial)







## $\color{yellow}{B.\ Reinforcement\ Learning\ Based\ Fine\ Tuning}$
Now above we saw how to finetune a foundational LLM model for different downstream tasks using SFT but for all those tasks we can also finetune a foundation model using RL. There are two ways to use RL to finetune :
- [Manual Reward Funtion Based RL](https://khetansarvesh.medium.com/llm-fine-tuning-using-rl-for-reasoning-857f9db05ba6) : Here we will see how to finetune using RL if you 'can design' a good reward function for your downstream task.
- (preferred)[Automatic Reward Function Based RL](https://khetansarvesh.medium.com/preference-alignment-0b67777fa7af) : Here we will see how to finetune using RL if you 'cannot design' a good reward function for your downstream task, via the help of preference dataset. There are multiple methods to do this : 
  - Reinforcement Learning using Human Feedback (RLHF) : trains a seperate reward model
  - (preferred) Direct Preference Optimization (DPO) : uses base LLM itself as reward model


> [!IMPORTANT]
> It has been proved previously that its better to first finetune LLM on any task using SFT and then finetune on the same task using RL, it gives better outcomes. This [notebook](https://colab.research.google.com/github/unslothai/notebooks/blob/main/nb/Qwen3_(4B)-GRPO.ipynb) from UnSloth follows the below recepie to convert Qwen3 from a non reasoning model to a reasoning model.
> <img width=500 src="https://github.com/khetansarvesh/NLP/blob/main/unitask_downstream_nlp/imgs/pipeline.png">







# $\color{cyan}{LLM\ Systems\}$
With foundation models that are able to do multiple tasks, you just need to do [prompting](https://www.promptingguide.ai/) to solve a single downstream task problem.
- [Single LLM System](https://github.com/khetansarvesh/NLP/blob/main/single_llm_sys.md)
- Multi LLM System
  - [LLM Workflows](https://github.com/khetansarvesh/NLP/blob/main/llm_workflow.md) : They follow static path
  - LLM Agents : They follow dynamic path. One way of determining this dynamic path is via using a planner agent. To learn how to design a good planner agent let's build a [Deep Research Agent](https://khetansarvesh.medium.com/deep-research-agent-2da7f25359b8). There are many frameworks that you can use to build this, few good ones are DSPY || [⁠AutoGen](https://github.com/microsoft/autogen) || [Langraph](https://www.langchain.com/langgraph) || [CrewAI](https://www.crewai.com/)
