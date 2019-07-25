## Kuzushiji MNIST character recognition

## Background
Fitting the Kuzushiji-MNIST character recognition dataset with convolution networks using Keras.

The dataset is available on Kaggle and is described here: https://www.kaggle.com/anokas/kuzushiji . It is a very similar to the classical MNIST (70000 28x28 grayscale images, 10 classes), but larger (Kuzuhiji-49 - 270912 28x28 grayscale images, 49 classes). 

## Goal
- Multiclass classification : Get > 95% accuracy in classifying the images into 49 classes.

## Challenges
- Size of dataset (270k images and 49 classes)

### Software/Packages/Programs

### Major
Name | Version 
--- | ---
Python | 3.6.6
Keras | 2.2.4
hyperopt | 0.2

### Minor
Name | Version 
--- | ---
matplotlib | 3.0.3
NumPy | 1.16.4
sklearn | 0.21.2

## Service

- Kaggle notebooks

## Status

- CNN + batchnorm + `hyperopt` --> train = 0.99, test = 0.95

## Todo
- Add some images to readme and the notebook


# Overview of approach

## Data and pre-processing
- Started with Kuzushiji dataset available in a convenient format.
- Train and test sets had similar class distributions and were **balanced**.
- Scaled features with SciPy's `MinMaxScaler`.
- Used `keras.utils.to_categorical` to one hot encode the labels.

## Baseline
- Feedforward NN with 1 hidden layer, 32 ReLU units.
- Accuracy: train = 0.77, test = 0.65

## Approach
- **Convolution** neural network.
- Used **batchnorm** greatly which greatly sped up learning.
- `hyperopt` for **hyperparameter optimization** to identify best kernel size, pool size and stride.
- Accuracy: train = 0.99, test = 0.94 --> overfitting

## Fine tune
- Added another conv-pool-batchnorm layer to increase number of features.
- Accuracy: train = **0.99**, test = **0.95**
