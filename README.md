# Data Preprocessing


# Representation Learning

### a. Next Word Prediction Task
   - LaMDA by Google
### b. Fill in the blank Task
### c. Multiple Tasks : Researchers thought that if we can train a model that can perform a set of multiple tasks then it will be able to generalize to other tasks that it has not seen during the training.(Well their hypothesis turned out to be correct !!)
   - [Model Alignment / Instruction Tuning](https://github.com/khetansarvesh/NLP/tree/main/multitask_downstream_task). Some famous models are
      - T5
      - GPT3 by OpenAI
      - [FLaN by Google](https://www.youtube.com/watch?v=SQ2CHiaENMc) :- Base Model used was Google LaMDA and Google LaMDA2
      - PALM by Google
      - U PALM by Google

   - [Preference Alignment / Post Training](https://medium.com/p/0b67777fa7af/edit). Some famous models are :
      - InstructGPT by openAI:- Based Model used was GPT3
      - [Google FLaN PALM](https://www.youtube.com/watch?v=NVITqBHqWM4&ab_channel=DataScienceGems):- Base Model used was PALM
      - Google FLaN T5:- Base Model used was T5
      - Google FLaN U PALM:- Base Model used was U PALM
      - [Google MED PALM](https://www.youtube.com/watch?v=KBVpxR3w5G8) :- Base Model used was FLAN PALM
      - [OPT-IML](https://www.youtube.com/watch?v=6YQbwZxTQX4&ab_channel=DataScienceGems) by Meta
      - Llama by Meta

# Downstream NLP
- With foundation models that are able to do multiple tasks, you just need to do prompting to solve a single downstream task problem
- But if prompting does not work well (incases where such a task was not trained during the training of multitask foundation model), then you can finetune the foundation models for specific tasks. More about this [here](https://github.com/khetansarvesh/NLP/tree/main/unitask_downstream_nlp)
  
# Resources Used to Develop This
1. [Standford CS224N - 2016](https://www.youtube.com/playlist?list=PLoROMvodv4rOhcuXMZkNm7j3fVwBBY42z)
2. [Standford CS224N - 2021](https://www.youtube.com/watch?v=rmVRLeJRkl4&list=PLoROMvodv4rMFqRtEuo6SGjY4XbRIVRd4)
3. [Standford CS224N - 2023](https://www.youtube.com/watch?v=LWMzyfvuehA&list=PL613dYIGMXoZ0Wl6tj8VvHaFUTAWE8fbW)
4. [Standford CS224D](https://www.youtube.com/playlist?list=PLlJy-eBtNFt4CSVWYqscHDdP58M3zFHIG)
5. [Speech and Language Processing Book](https://web.stanford.edu/~jurafsky/slp3/)
