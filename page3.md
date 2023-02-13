--- 
title: "Feature Engineering"
date: 2023-02-01
layout: default
rank: 3
---
## Feature Engineering

What is **feature engineering** and why is it important?

A *feature* represents any measurable input that can be used for analysis. 

*Feature engineering* takes raw observations and converts them into useful features for use in supervised learning. It is an important step in the data science pipeline because it has a direct impact on being able to create models with better accuracy. 

Feature engineering consists of various processes, including feature creation, transformations, extractions, EDA, and Benchmark. 
- Feature creation involves adding or removing features to utilize features that will be most helpful for the model.
- Transformations involve taking a function to convert a feature from one representation to another.
- Feature extraction involves extracting features from a dataset without distorting its original relationships in order to identify useful information that is contained.
- EDA, shown in the previous blog post, is used to better understand the data by exploring its properties. 
- Benchmark is the step in which you measure how your model against a known dependable model to compare its performance ([Towards Data Science](https://towardsdatascience.com/what-is-feature-engineering-importance-tools-and-techniques-for-machine-learning-2080b0269f10))

There is not any more feature engineering to be done because the dataset already represents the important, compressed data as a result of a **principal component analysis (PCA)** transformation.

### Principal Component Analysis (PCA) Transformation

The [credit card dataset](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) that I am working with has already gone through a PCA transformation and been extracted and reduced down to 28 features. 'Time' and 'Amount' are the only features that has not been transformed.


A PCA transformation is a dimensionality-reduction method that transforms a large set of variables into a smaller one while still keeping most of the original information. Essentially, it reduces the number of variables while preserving as much information as possible ([builtin](https://builtin.com/data-science/step-step-explanation-principal-component-analysis)). The understanding of PCA assumes a linear algebra background, but to put it simply, PCA essentially uses variance to quantify the amount and the parts of the data that are important. Consequently, the components that have higher variance hold more information. 

Wikipedia defines PCA as

*an orthogonal linear transformation that transforms the data to a new coordinate system such that the greatest variance by some scalar projection of the data comes to lie on the first coordinate (called the first principal component), the second greatest variance on the second coordinate, and so on.*

