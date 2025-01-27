# Data Preprocessing


# Representation Learning / Pre-Training

# UniTask Downstream NLP
- Here we make different models for different types of downstream tasks. You can learn more about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)
- No one does this anymore with the rise of one single model that can do multiple tasks

# MultiTask Downstream NLP
   - Here we create one single model which can handle multiple downstream tasks, this is called [Model Alignment / Instruction Tuning](https://github.com/khetansarvesh/NLP/tree/main/multitask_downstream_task). Some famous models are
      - T5
      - GPT3 by OpenAI
      - LaMDA by Google
      - PALM by Google
      - U PALM by Google
      - FLAN PALM by Google

   - [Preference Alignment / Post Training](https://medium.com/p/0b67777fa7af/edit). Some famous models are :
      - InstructGPT by openAI:- Based Model used was GPT3
      - Google FLANG LaMDA and LaMDA2:- Base Model used was LaMDA
      - [Google FLANG PALM](https://www.youtube.com/watch?v=NVITqBHqWM4&ab_channel=DataScienceGems):- Base Model used was PALM
      - Google FLANG T5:- Base Model used was T5
      - Google FLANG U PALM:- Base Model used was U PALM
      - [Google MED PALM](https://www.youtube.com/watch?v=KBVpxR3w5G8) :- Base Model used was FLAN PALM
      - [OPT-IML](https://www.youtube.com/watch?v=6YQbwZxTQX4&ab_channel=DataScienceGems) by Meta
      - Llama by Meta

   -  Now once we have a model that can do multiple tasks, we can now finetune such a model for one specific task. For instance
      -  Models finetuned for Chatbot Tasks
         - ChatGPT / GPT3.5
         - CLaude
         - Dolly 2.0 by Databricks
         - Alpaca-7B | 13B Model by stanford : Fine tuned on llama-7B | 13B respectively
         - Vicuna 7B | 13B Model : Fine tuned on llama-7B | 13B respectively
         - Lambda 2 Chat 7B | 13B | 70B : Fine Tuned on Lambda2

      - Models finetuned for Code Generation Task
         - CodeWhisper
         - CodeX / Github Copilot : Fine tuned on GPT3 using publicly available code on github
         - CodeBERT
         - PyMT5



# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
