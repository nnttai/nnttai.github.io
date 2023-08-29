---
author: "Nguyen Nhi Thanh Tai"
title: "Basic concept in machine learning"
date: 2023-08-28
toc: true
---

# TL;DR

- In this posts, we will explain some very basic concepts in machine learning and used in deep learning also.

## 1. What is machine learning?

- Tom Mitchell provides a more modern definition: "A computer program is said to learn from experience E with respect to some class of tasks T and performance measure P, if its performance at tasks in T, as measured by P, improves by experience E".
- For example:
  - Building an email spam classifier:
    - T is the task which classifies which email is spam.
    - P is the accuracy of the classifier.
    - E is the loss function used for improve P accuracy.

## 2. What is supervised-learning?

- In supervised-learning, we are given a dataset that already know about each data point's label. Having the idea of how the output should be look like and the sense of the relationship between input and output.
- Supervised learning is categorized into "REGRESSION" and "CLASSIFICATION" problems:
  - Regression problem definition: We trying to predict results within a continuous output, meaning that we are trying to map input variables to some continuous function.
  - Classification problem definition: Trying to predict results in a discrete. In other words, we try to map input into discrete categories.
- For example:
  - Supervised-learning: Given data of many pictures of cat and dog, given new image, your mission is classify that image is belong to cat or dog.
  - Regression problem: Predict the price of stocks in the future -> price is continuous variable -> regression problem
  - Classification problem: Predict the weather will rain or not at tomorrow -> Rain:0 - Not rain : 1

## 3. What is unsupervised-learning?

- Unsupervised learning, also known as unsupervised machine learning, uses machine learning algorithms to analyze and cluster unlabeled dataset. This algorithm discover hidden patterns or data groupings without the need for human intervention.
- Its ability to discover similarities and differences in information make it the ideal solution for exploratory data analysis, cross-selling strategies, customer segmentation.
- Unsupervised learning models are utilized for three main tasks: clustering, associations and dimension reduction.
- Clustering: Clustering algorithms are used to process raw, unclassified data object into groups represented by structures or patterns in the information
- Association rules: An association rule is rule-based method to finding relationships between variables in a given dataset.
- Dimensionality reduction: Dimensionality reduction is a technique used when the number of features, or dimensions, in a given dataset is too high. It reduces the number of data inputs to manageable size while also preserving the integrity of the dataset as much as possible.

## 4. What is semi-supervised learning?

- In a nutshell, semi-supervised learning (SSL) is a machine learning technique that uses a small portion of labeled data and lots of unlabeled data to train a predictive model.
- Semi-supervised learning bridges supervised learning and unsupervised learning techniques to solve their key challenges. With it, you train and initial model on a few labeled samples and then iteratively apply it to the greater number of unlabeled data.

## 5. What is reinforcement learning?

- Reinforcement learning in formal terms is a method of machine learning wherein the software agent learns to perform certain actions in an environment which lead it to maximum reward. It does so by exploration and exploitation of knowledge it learns by repeated trials of maximizing the reward.

## 6. Model representation

### 6.1 Notation

- To establish notation for future use, we'll use $x^{(i+1)}$ to denote the "input" variables, also called input features, and $y^{(i)}$ to denote the "output" or target variable that we are trying to predict. A pair ($x^{(i)}$, $y^{(i)}$) is called training example. A list of m training examples called training set ($x^{(i)}$, $y^{(i)}$), *i* = 1,...,m.
- To describe the supervised learning problem slightly more formally, our goal is, given a training set, to learn a function h(x)->y so that h(x) is a "good" predictor for the coressponding value of y. This function h is called a hypothesis. Like below image:

{{< figure src="/images/hypothesis.jpg" alt="image" caption="figure-normal (without any classes)" >}}
