# Riiid! Answer Correctness Prediction 

This is a collection of my code from the [Riiid AIEd Challenge 2020](https://www.kaggle.com/c/riiid-test-answer-prediction) Kaggle competition.

#### Preprocessing

| File        | Comment     |
| ----------- | ----------- |
|  [preprocessor.ipynb](preprocessor.ipynb)  | Preprocess data by looping on numpy arrays. The code as is can process the entire train.csv file in aprox. ~40 min on an `i7-7700` `64GB` machine.|
| [kmeans_&_BKT_input.ipynb](kmeans_&_BKT_input.ipynb) | Cluster the question tags and build the input for the BKT model|

#### Models

| File        | Comment     |
| ----------- | ----------- |
| [LightGBM.ipynb](LightGBM.ipynb) | The code to train the LightGBM Model `CV: 0.794, LB: 0.795` that landed me in 126th place out of 3395 teams. |
| [NeuralHLR.ipynb](NeuralHLR.ipynb) | Tensorflow implementation of a Neural HLR model inspired by [[1]](https://arxiv.org/pdf/2004.11327.pdf). The goal was to ensemble this model with the Light GBM model, but due to time constraints, I opted to focus on feature engineering. |
| [factorization_machine.ipynb](factorization_machine.ipynb) | The code to preprocess and train a Factorization Machine model. Due to limitations of the [xLearn](https://github.com/aksnzhy/xlearn) library, I was unable to get a successful submission. |
| [tensorflow_factorization_machine.ipynb](tensorflow_factorization_machine.ipynb) | Factorization Machine algorithm implemented in Tensorflow. I never attempted to make a submission with this model as handling the sparse data proved to be troublesome and expensive. <small>*Note: this code is still messy and the implementation needs verified; uploading for personal reference.*|

#### Other 

| File        | Comment     |
| ----------- | ----------- |
| [Bayesian 1PO IRT](https://github.com/blei-lab/edward/blob/master/examples/irt.py)      | This code was modified and adapted to the provided data to train an Bayesian IRT model to measure a student's ability and a question/tag's difficulty and discrimination. This code requires a specific environment to run. Specifically, `numpy==1.18` and `Tensorflow==1.6`|
| [Individualized BKT](https://github.com/myudelson/hmm-scalable)   | The code used to train a BKT model to measure each students chances of mastering a Knowledge Unit (kmeans-clustered tag), as well as their chances of *guessing* or *slipping* when answering a question related to the particular tag. | 

