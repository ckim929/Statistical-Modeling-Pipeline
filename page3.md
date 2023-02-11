--- 
title: "Feature Engineering"
date: 2023-02-01
layout: default
rank: 1
---

What is **feature engineering** and why is it important?

A feature represents any measurable input that can be used for analysis. 
Feature *engineering* takes raw observations and converts them into useful features for use in supervised learning. 

Feature engineering is an important process in the data science pipeline because it has a direct impact on creating models with better accuracy. 

Feature engineering consists of various processes, including feature creation, transformations, extractions, EDA, and Benchmark ([Towards Data Science](https://towardsdatascience.com/what-is-feature-engineering-importance-tools-and-techniques-for-machine-learning-2080b0269f10))

The [credit card dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) I am working with is the result of a PCA transformation.

A **PCA transformation** is a dimensionality-reduction method that transforms a large set of variables into a smaller one that still keeps most of the original information. Essentially, it reduces the number of variables while preserving as much information as possible ([builtin](https://builtin.com/data-science/step-step-explanation-principal-component-analysis)). Without going into too much of the mathematical details, PCA essentially uses the variance to quantify the amount and the parts of the data that is important. Data that has higher variance holds more information. 

Wikipedia defines PCA as

*an orthogonal linear transformation that transforms the data to a new coordinate system such that the greatest variance by some scalar projection of the data comes to lie on the first coordinate (called the first principal component), the second greatest variance on the second coordinate, and so on.*

This dataset collect and analyzed by Worldline and the [MLG](http://mlg.ulb.ac.be/) of ULB has already gone through a PCA transformation and been reduced down to 28 features. 'Time' and 'Amount' are the only features that has not been transformed. 
