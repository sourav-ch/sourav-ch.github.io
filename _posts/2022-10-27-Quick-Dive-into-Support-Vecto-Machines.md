---
title: Quick Dive into Support Vector Machines
tags: [SVMs, Data Science, ML]
style: border
color: primary
description: A quick ML hands-on.
---


Support Vector Machines (SVMs) are a powerful and flexible model used for classification, regression, and even outlier detection, handling both linear and non-linear problems. To understand how SVMs work, let’s use a simple example. Imagine we have two categories, red and blue, with data points represented by x and y coordinates. Our goal is to create a classifier that can determine whether a pair of (x, y) coordinates belongs to the red or blue category. We plot the labeled training data on a plane, and the SVM algorithm finds a hyperplane (a line in two dimensions) that best separates the red and blue points. This line, known as the decision boundary, classifies points on one side as blue and those on the other side as red.

![](https://d33wubrfki0l68.cloudfront.net/7fe2455c93b278f745d39908183732336b20f4be/709b4/static/57fd2448dfb67cfff990f32191463e80/6d7b8/plot_hyperplanes_2.png)

## Linear SVM Classification

In Linear SVM Classification, the hyperparameter ‘c’ controls the type of SVM. It has two types: A. **Hard Margin**: No outliers are allowed on the boundary. B. **Soft Margin**: Outliers are allowed within the boundary. When the value of ‘c’ is smaller, it results in wider boundaries, allowing more margin violations.

![](https://miro.medium.com/max/552/1*CD08yESKvYgyM7pJhCnQeQ.png)

Unlike logistic regression classifiers, SVMs do not produce probabilities. However, you can use the **SGDClassifier**, which employs Stochastic Gradient Descent to train a linear SVM classifier. While it doesn't converge as quickly as **linear SVC**, it is suitable for handling large datasets.

### Non-linear SVM Classification

In some cases, datasets are non-linear, and a simple linear approach won't work. One way to address this is by adding more features, such as polynomial features, to better represent the data.

#### Polynomial Kernel
Adding polynomial features can work with various machine learning algorithms, but if the polynomial degree is too high, it can become slow. Conversely, a low degree might not capture complex datasets well. However, SVMs use a technique called the "kernel trick," which allows you to achieve the effects of adding high-degree polynomial features without actually doing so.

#### Adding Similarity Features
Another approach to solving non-linear problems is to introduce similarity features, which measure how much a given instance resembles a particular reference point or landmark. This helps the model handle non-linear patterns more effectively.

#### Gaussian RBF Kernel
Like the polynomial feature method, the similarity features method is also applicable to many machine learning algorithms. The **Radial Basis Function (RBF) kernel** has two important hyperparameters: ‘gamma’ and ‘c’. The ‘c’ parameter is a regularization factor, and as its value decreases, the model becomes more regularized. Increasing ‘gamma’ narrows the bell-shaped curve, which means each instance has a smaller influence range. As ‘gamma’ is also a regularization parameter, if your model is overfitting, reducing its value can help.

### SVM Regression
SVMs are not just for classification; they can also be used for regression. The key difference is in the objective: instead of finding the widest possible margin between two classes, SVM regression aims to fit as many instances as possible within the margin while still limiting margin violations.

### Decision Functions and Predictions
In linear SVM classification, the model predicts the class of a new instance by computing a decision function. If the result is positive, the instance is classified into the positive class; otherwise, it is classified into the negative class.


