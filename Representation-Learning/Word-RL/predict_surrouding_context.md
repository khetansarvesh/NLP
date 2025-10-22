# Predict W(t-1),W(t-2).... , W(t+1),W(t+2) …… | W(t)

- As you can see from the formulation, here given a target word, the probability of the neighbouring (surrounding) words in a pre-defined window has to be maximized.

- Such models are called Neural MASKED Language Models (nMLM). You can use any sequential model discussed [here](https://pub.towardsai.net/deep-learning-for-time-series-forecasting-ff5c8bf35134) to perform this task.

- Below we will see FFNN MLM - this was given a special name called Skip Gram (SG) model [Word2vec]

