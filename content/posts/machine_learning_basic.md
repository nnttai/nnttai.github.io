---
author: "Nguyen Nhi Thanh Tai"
title: "Basic concept in machine learning"
date: 2023-08-28
toc: true
---

# TL;DR

- In this posts, we will explain some very basic concepts in machine learning and deep learning.

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

- As mentioned above, about the definition of machine learning, this part will describe that quote in more imaginable way:
  - Task T is the model or in mathematically way, a function h(x)->y with input is vector x and predict the value y.
  - Performance P is the metric of the model, which will be used to verify that model is good or not.
  - Experience E is the cost function of model, a special function which will help model ***LEARNING***.

### 6.1 Notation

- To establish notation for future use, we'll use $x^{(i+1)}$ to denote the "input" variables, also called input features, and $y^{(i)}$ to denote the "output" or target variable that we are trying to predict. A pair ($x^{(i)}$, $y^{(i)}$) is called training example. A list of m training examples called training set ($x^{(i)}$, $y^{(i)}$), *i* = 1,...,m.
- To describe the supervised learning problem slightly more formally, our goal is, given a training set, to learn a function h(x)->y so that h(x) is a "good" predictor for the coressponding value of y. This function h is called a hypothesis. Like below image:

{{< figure src="/images/hypothesis.jpg" alt="image" caption="general machine learning flow" >}}

### 6.2 Cost function

- At mentioned above, we have function h(x)->y is our model representation, but to make that model have ability to learn, we need cost function. Generally, cost function will minimize the gap between true value and the value predicted by our model.
- For more detail, we will use regression problem to describe what is cost function.

  - The cost function of regression problems with 2 parameters usually have this form:
    - $J(\theta_0, \theta_1)=\frac{1}{2m}\sum_{i=1}^m{(\hat{y_i}-y_i)}^2$
  - This function called **Mean squared error**. As you can see, if the gap between predicted value and true value is to high, the value of cost function is high too and vice versa.
  - So the question is, how to minimize this cost function or in other word, how to make the predicted value as similar as true value. We will go to the next part.

### 6.3 How the model learn?

- What is the magic that make model have ability to learn? Go back to the cost function above, we can see 2 strange sign $({\theta_0},{\theta_1})$, these two sign called theta, which help model learning.
- To be more clearly, we have hypothesis function h(x) look like this
  - $h(x)={x_0}{\theta_{0}}+{x_1}{\theta_{1}}+...+b$ and $\hat{y}=h(x)$
- Two thetas is usually called **weight** of the model, which will controll the learning path of the model. But only thetas cannot help the model learn, we need a algorithm called gradient descent, gradient descent have many variant which will be mentioned in another blog.

#### 6.3.1 Derivative

- To understand gradient descent, we need to know about derivative, but the math will be explained later in code, at this moment, just the concept.
  - Derivative definition by wikipedia:
    > The derivative shows the sensitivity of change of function's output with respect to the input.
  - This is how I think in case you fell that definition is so complicated:
    - Generally, it's all about the relationship between input and output, in our case, input is vector x and output is $\hat{y}$.
    - Each component $x_i$ in vector $x$ go with $\theta_{i}$, so when we derivate the hypothesis function, $\theta$ is the factor affected the result of the derivate of the function.
    - So now we have a clearly view about the connection between $\theta$ and the result of our hypothesis function $\hat{y}$.

#### 6.3.2 Gradient descent

- Lady and gentlement, the main part, the heart, the magic of almost every machine learning model and deep learning model is here, ***GRADIENT DESCENT***.
- Generally, gradient descent is the algorithm used to tuning the value of $\theta$, which will help the model find out which value of $\theta$ make the cost function reaches the minimum value.
- The form of gradient descent is:
  > $\theta_{j}=\theta_{j}-\alpha\frac{\partial}{\partial_{\theta}}J({\theta_{0}}, {\theta_{1}})$.
- So the value of $\theta$ is tuned by the multiplication of $\alpha$ and derivative of cost function and $\alpha$ is the learning rate which controll the value changing small or big.
- So now I will explain why subtraction, imagine about the bowl like and the optimal value of the $\theta$ is the lowest point of the bowl, if the value of $\theta$ is on the right so the value should go from right to left and at that time the value of $\alpha\frac{\partial}{\partial_{\theta}}J({\theta_{0}}, {\theta_{1}})$ is positive so we need to subtract it, when the $\theta$ is on the left, the value should go from right to left, at that time $\alpha\frac{\partial}{\partial_{\theta}}J({\theta_{0}}, {\theta_{1}})$ is negative so subtraction the negative value is equal to plus positive value, so $\theta$ will go from left to right.

{{< figure src="/images/Gradient_descent.jpg" alt="image" caption="From Machine learning course of Andrew Ng" >}}
