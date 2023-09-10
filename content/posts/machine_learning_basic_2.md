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

- From the example above, you can see the fact that, the most important thing is get the good result in test set (in modeling phrase only*). To reach the good performance on test set, we should repeat the tuning process many times to have good parameter set. Using metric on those three set will help you do that tuning process in easier and more logical way rather than just tune it randomly.

*- NOTE:* Actually, when we deploy model in production environment, the most inportance is the result when the model is used in real life. Which will be talked in blogs about MLOPs.  

### 2.2 Error, Bias and Variance

### 2.2.1 Error

- In machine learning, an error is a measure of how accurately an algorithm can make predictions for particular unknown dataset. There are mainly two type of errors in machine learning, which are:
  - **Reducible error**: Theses error can be reduced to improve the model accuracy. Such errors can further be classified into bias and variance.

- **Irreducible error**: These errors wills alway be present in the model regardless of which algorithm has been used. The caused of these errors is unknown variables and cannot be reduced.

{{< figure src="/images/bias-and-variance-in-machine-learning2.jpg" alt="image" caption="From Javatpoint's blog" >}}

### 2.2.2 Bias

- Generally, bias is a difference between your model's prediction and expected value. We can have two case of bias:
  - Low bias: The model is low bias when the difference between model's prediction and your expected value is low, which means your model can learn the relationship between data and output.
  - High bias: The model is high bias when the difference between model's prediction and your expected value is high, which means the model cannot learn anything from your data. called **Underfit**.
- **Underfit** is when your model is useless, dont has ability to make good predict.
- High bias mainly occurs due to much simple model, these are some method to reduce high bias:
  - Increase the input features.
  - Decrease the regularization term.
  - Use more complex model.

### 2.2.3 Variance

- Variance, generally, estimates how good your model is when your model make prediction on new dataset, for example, you train your model in training set and make prediction on test set. We also have two case of variance:
  - Low variance: when your model doing good on **test set**, so it is low variance
  - High variance: when you model doing good on **train set**, but bad on **test set**, so it call high variance. High variance usually because your model is so complicated, and it can learn by heart the relationship in each data point in training set, that why it good on training set. Also called **Overfit**.
- **Overfit** is when your model doing so good on train set but so bad in test set.
- Ways to reduce high variance:
  - Reduce the input feature or number of parameter in model.
  - Use simpler model or algorithm.
  - Increase the training data.
  - Increase the regularization term.

## 2.3 Why you should need metric?

- The goal of building a model is creating a model that has ability to make good prediction on data which model haven't seen before. Because building a good model is a iterative process, you evaluate the model on test set and tuning it until it reach good performance. The reason why you cannot use loss function are:
  - Loss function cannot be used for checking that the model is underfit or overfit.
  - Loss function can just be used for checking the model is optimized or not and metric is used to know that the model is doing good or not.
  - You choose the model and use loss function to optimize the model after that you use the metric the evaluate that the optimization process is good or not by use that model to make prediction on test set.
