---
title: Machine Learning Basics
tags: [AI, ML]
style: fill
color: light
description: Introduction to ML 
---

## Why ML?

Machine learning can simplify tasks like building a spam filter. Instead of manually creating rules for detecting spam, machine learning automatically learns patterns from spam emails, making the system shorter and easier to maintain. While spammers may try to bypass filters by changing words or formats, machine learning-based filters adapt by recognizing these changes. Additionally, machine learning is useful for problems without a clear algorithm, like speech analysis, and can uncover hidden patterns in large datasets, a process known as data mining.

## Types of Machine Learning Systems

There are many types of machine learning systems. This is classified as follows:

- Whether they are trained on human supervision
- Whether they can learn incrementally or on the fly
- Whether they work on by simply comparing the data points or detect patterns

## Types of ML Systems

Machine learning systems are categorized based on the supervision they receive during training, and there are four main types:

Supervised Learning: The training data includes labeled solutions. Common tasks include classification, like spam filters, and predicting numeric values. Algorithms include K-nearest neighbors, linear/logistic regression, SVMs, decision trees, and neural networks.

Unsupervised Learning: The training data is unlabeled. It includes clustering (K-means, DBSCAN), anomaly detection (One-class SVM), dimensionality reduction (PCA, t-SNE), and association rule learning (Apriori). It helps simplify data and uncover hidden patterns.

Semi-Supervised Learning: Combines a small amount of labeled data with a large amount of unlabeled data. Google Photos is an example, using a mix of basic algorithms like DBNs and RBMs.

Reinforcement Learning: An agent learns by observing the environment, performing actions, and receiving rewards. It aims to optimize its strategy over time. An example is DeepMind's AlphaGo, which learned from millions of Go games to beat the world champion.


## Batch And Online Learning

Batch Learning: In batch learning, the model is trained on all available data at once, which can be time-consuming and resource-intensive. This training is done offline, and if new data comes in, the system must be retrained from scratch, often daily or weekly. It's inefficient for large datasets and expensive in terms of resources.

Online Learning: Online learning trains the system incrementally by feeding data sequentially, making it faster and more adaptable. It’s ideal for continuous data streams, like stock price prediction, and works well with limited resources. It saves resources by discarding old data once it's learned. However, it can struggle with bad data, such as sensor errors, and may require monitoring or temporarily halting the learning process to maintain performance.


## Instance based vs Model based learning

Instance-Based Learning: The system memorizes examples and generalizes new cases by comparing them to previously learned examples using a similarity measure.

Model-Based Learning: In this approach, a model is created to make predictions and generalize examples.

Utility/Fitness Functions: Measure how good the model is.
Cost Functions: Measure how bad the model is. For example, in linear regression, the cost function (MSE) calculates the difference between predicted and actual values, aiming to minimize that difference.

## Challenges of ML


Bad Data
a. Insufficient Data: Machine learning requires large datasets for most algorithms to perform well.
b. Poor Quality Data: Errors, outliers, and noise in the data make it difficult for the system to detect patterns and negatively impact performance.
c. Irrelevant Features: The success of a model depends on using relevant features for training. Feature engineering involves selecting the most useful features, reducing dimensions, or creating new features from the data.

Bad Algorithms
a. Overfitting: The model performs well on training data but struggles to generalize. This occurs when the model is too complex for the data and can be prevented using regularization.
b. Underfitting: The model is too simple to capture data patterns. Solutions include using a more powerful model, improving features, or reducing constraints.

## Testing and Validating

The best way to assess a model's performance is by testing it on new data. To do this, the data is divided into training and test sets. The error rate on the test set is known as the generalization error. If the training error is low but the generalization error is high, it indicates the model is overfitting the training data.