# Rocket League Trickshot Classifier

## Introduction

The aim of this project was to train a machine learning model that can effectively classify trickshots in the video-game Rocket League.

The project was done as part of the Introduction to Machine Learning course at the Vienna University of Technology.

## Data

The dataset is in tabular form (CSV), containing 297 separate trick shots. Each trickshot consists of summary statistics and arbitrarily many timesteps, each containing an in-game metric and a keyboard input. The summary statistics are the median and the skew of their trickshot's respective metrics.

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

## Approach

TODO

## Results

TODO
