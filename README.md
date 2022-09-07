# Correlation Matrix for Polynomial Features Regression

Fitting a good regressor with polynomial features obtained from significant features, according to correlation matrices.

## Problem Overview

[Regressors] are very useful models to predict future values using historical data, especially considering continuous numeric data. However, such models have limitations when dealing with data having a high dimensionality or when the data has a polynomial behavior in space. In these cases, a linear regression is not sufficient to learn the data behavior:

![correlation_matrix_for_regression1](https://user-images.githubusercontent.com/33037020/188773236-2e007644-f38d-40a3-a7e6-8c442a0091e7.png)

Different techniques can help do mitigate this issue and find a simple regression model able to return predictions with small errors. Some of them include [polynomial feature transformation] and [feature selection].

## Analysis Introduction

In datasets with multiple independent variables it is very common for some of them to not be really independent. Therefore, these variables can be derived by performing some operations on other variables available on the same dataset. This behavior can be identified by observing the correlation between independent variables pairs. If a variable pair has a high degree of correlation (or covariance), they probably carry the same information. In this case, one of the variables that form the pair can be discarded without significant loss of information.

In this analysis, we show how to analyze correlation between features and select the most valuable ones using a correlation matrix. Then, a polynomial regression is achieved by using polynomial features obtained from the original ones. With the polynomial representation, in practice, we get a polynomial kernel transformation of our data to a higher dimensionality.

In a higher dimensionality space we may find information on interactions between features (i.e. when multiplying *feature1* with *feature2*) while we can also amplify the signal of all features by having them squared (i.e. when multiplying *feature1* with *feature1*). With the additional information provided by the polynomial features, a more suitable regressor can be fit:

![correlation_matrix_for_regression2](https://user-images.githubusercontent.com/33037020/188773252-fa8ca5af-850f-4a41-85ae-78ce19c9ced5.png)

[//]: #

[Regressors]: <https://en.wikipedia.org/wiki/Linear_regression>
[polynomial feature transformation]: <https://scikit-learn.org/stable/modules/generated/sklearn.preprocessing.PolynomialFeatures.html>
[feature selection]: <https://www.analyticsvidhya.com/blog/2021/06/feature-selection-techniques-in-machine-learning-2/>
