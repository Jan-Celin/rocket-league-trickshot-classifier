# Rocket League Trickshot Classifier

## Introduction

The aim of this project is to train a machine learning model that can effectively classify trickshots in the video-game Rocket League.

This project was done as part of the Introduction to Machine Learning course at the Vienna University of Technology.

## Data

The dataset is in tabular form (CSV), consisting of two files:
- `rocketskillshots_train.csv` - training data containing labeled trickshots;
- `rocketskillshots_test.csv` - test data used for evaluation.

Each trickshot consists of summary statistics and arbitrarily many timesteps, each containing an in-game metric and logs of keyboard inputs. The summary statistics are the median and the skew of their trickshot's respective metrics.

The following in-game metrics are measured:

- BallAcceleration: The current acceleration of the football;
- DistanceWall: The current player's distance to the closest wall;
- DistanceCeil: The current player's distance to the ceiling;
- DistanceBall: The current player's distance to the ball;
- PlayerSpeed: The current speed of the player's car;
- BallSpeed: The current speed of the ball.

The following keyboard inputs are tracked:

- up
- accelerate
- slow
- goal
- left
- boost
- camera
- down
- right
- slide
- jump

The target value of is the trickshot class, which can be one of the following:

- -1: noise (no trickshot)
- 1: ceiling shot
- 2: power shot
- 3: waving dash
- 5: air dribble
- 6: front flick
- 7: musty flick

Some columns contained missing values. Several methods of handling them were tested:
- filling them with zeros,
- filling them with the columns mean,
- interpolation

## Approach

Several different machine learning models were trained and tested, including:

- Logistic regression
- Decision tree
- Random forest
- Multi-layer perceptron
- Model ensembles

Hyperparameter tuning was performed for several models using randomized and grid search.

Since each trickshot had multiple records in the dataset, the general approach was to classify each record independently and assign the final trickshot label via majority voting. More sofisticated models could use all metrics at once to create the prediction, however, that was out of this course's scope.

## Results

Model performance was evaluated using accuracy score and confusion matrices.

Among of the five tested methods, random forest and decision tree models performed best. This can likely be attributed to the fact that those models most effectively model the algorithmical nature of the in-game trickshot assignment. 

The detailed performances of each of the models can be found in the notebook in the root of the repository.
