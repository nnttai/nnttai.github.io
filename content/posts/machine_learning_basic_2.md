---
author: "Nguyen Nhi Thanh Tai"
title: "Machine learning part 2"
date: 2023-09-06T20:20:48+07:00
toc: true
series: 
  - machine-learning-basic
tags:
  - ML
  - basic
---
<!--more-->

In the first blog in this series, we explained about task T and experience E, two parts that help building a model, but to evaluate the model we need something called ***METRIC***.

## 1. What is metric?

- Performance metrics in machine learning are essential for assessing the effectiveness and reliability of the models. They're key element of every machine learning pipeline, allowing developers to fine-tune their algorithms and drive improvement.
- The metrics can be broadly categorized into two main types: regression and classifications.

## 2. Why metric important?

- Some people argue that we can use loss function to evaluate the model performance, through this logic *"We always want that the loss function as small as possible, so that if the value of loss function small, the model is good"*. That sound great, however it not easy like that. To make more clearly about why loss function cannot be used to evaluate model performance, we should know some concept in evaluate data:
  - Train validation test split
  - Bias
  - Variance
  - Overfitting
  - Underfitting

### 2.1 Train validation test split

- At first, in every machine learning or deep learning project, we need to split the dataset intp three subsets smaller, called: 
  - Training set: is the data *used by the model in training phrase.*
  - Validation set: is the data used to *evaluate the training procedure.*
  - Test set: is the data used to *evaluate the model performance when the model make predict on unknown input.*

- Why we need to split the data? 
  - To be more imaginable, suppose you are the student with the target is winning the first prize in Olympic Math.
  - You go to school and learn knowledge everyday, day by day, so *day by day* is your learning phrase and *knowledge* is your train set.
  - When the competition day is near, your teacher will give you some sample tests and you do it, so *sample tests* is the validation test. 
  - However, the main purpose is do great on real test at the competition, *real test* is the test set.

- From the example above, you can see the fact that the most important thing is get the good result in test set. To reach the good performance on test set, we should repeat the tuning process many times to have good parameter set. Using metric on those three set will help you do that tuning process in easier and more logical way rather than just tune it randomly.

### 2.2 Bias and variance
