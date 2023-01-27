--- 
title: "Data Cleaning and Exploratory Data Analysis (EDA)"
date: 2023-01-25
---

## Data Cleaning
The first step of the data science pipeline is data cleaning. **Data cleaning** is the process of fixing or removing incorrect, duplicate, or incomplete data within a dataset. The dataset I am working with contains only numerical variables resulting from a principla component analysis (PCA) transformation.

### A Quick Snippet on PCA Transformation
A PCA transformation is a dimensionality-reduction method that transforms a large set of variables into a smaller one that still keeps most of the original information. Essentially, it reduces the number of variables while preserving as much information as possible ([builtin](https://builtin.com/data-science/step-step-explanation-principal-component-analysis)). Without going into too much of the mathematical details, PCA essentially uses the variance to quantify the amount and the parts of the data that is important. Data that has higher variance holds more information. 

Wikipedia defines PCA as

*an orthogonal linear transformation that transforms the data to a new coordinate system such that the greatest variance by some scalar projection of the data comes to lie on the first coordinate (called the first principal component), the second greatest variance on the second coordinate, and so on.*

This dataset collect and analyzed by Worldline and the [MLG](http://mlg.ulb.ac.be/) of ULB has already gone through a PCA transformation and been reduced down to 28 features. 'Time' and 'Amount' are the only features that has not been transformed. 

Upon initial analysis, the data I am working with here is relatively clean. I've checked for null and duplicate values using **data.isnull().sum()** and **data.duplicated()**. I found some duplicate values that I've removed. All of the features are numerical variables labeled **V1, V2,..., V28**. However, because data cleaning is an iterative process it may be possible that I have to come back to this step again.

## Exploratory Data Analysis (EDA)
It's important to understand the data to gather as much insight as possible from it. This step is all about making sense of the data by looking for patterns, spotting anomalies, and checking assumptions through summary statistics and visualizations ([towardsdatascience](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)). 

After reading in the data, I used the .shape function of the pandas library to return the shape of the dataframe. We can see that there are 284807 rows and 31 columns. 

![datashape](https://user-images.githubusercontent.com/86743951/215136138-7f1a73b0-2ce0-4473-a3be-2157d6bf219f.png)

I used the *.head()* function of the pandas library to look at the first five observations of my dataset. 

![head](https://user-images.githubusercontent.com/86743951/214944882-7877bba7-3458-4de6-8bd7-3e98fd4761cb.png)


The **.info()** function is also useful pandas function for printing important information such as its index dtype and columns, non-null values and memory usage.

![datainfo](https://user-images.githubusercontent.com/86743951/215006655-682f7a9b-632b-4d45-895e-bbef744514e1.png)


Next, I used the *is.null().sum()* function of the pandas library to see if there existed any null values in the dataset. The dataset does not contain any null values.

![null_values](https://user-images.githubusercontent.com/86743951/215003746-1351832a-c590-4fb7-b0e0-723957f149c6.png)

I also used the *.duplicated()* to see if there existed any duplicate rows in my dataset. The *.duplicated()* function of the pandas library returns a boolean series denoting duplicate rows. I found that my dataset contains 1081 duplicated rows. 

![duplicates](https://user-images.githubusercontent.com/86743951/215144874-93d46864-71d0-40a3-ad48-e42dd7f54fac.png)

I'll drop the duplicated rows using the pandas drop_duplicates() function.

![drop_duplicates](https://user-images.githubusercontent.com/86743951/215145698-ac4c8bfd-4eff-4def-aee9-c8dcf5c436eb.png)


## Regression vs Classification
To further conduct EDA on the dataset, it is important to understand the difference between **regression** and **classification**. Both are types of **supervised machine learning (ML) algorithms**, meaning it uses labeled datasets to train algorithms to predict outcomes or classify data. Unsupervised learning uses ML algorithms to analyze and cluster *unlabeled* datasets without the need for human intervention. 

So what is the difference between regression and classification?
Regression algorithms are used to predict a continuous value using the input variables. Regression predicts continuous variables by finding correlations between the dependent and independent variables (i.e. predicting house price, sales, temperature). 
Classification algorithms use input variables to approximate a *discrete* output variable. The dataset is divided into different categories and the algorithm estimates discrete values (i.e. 0 and 1, yes and no, true or false). Some examples of classification problems include predicting whether someting is spam or not and sentiment analysis (positive or negative).

As such, the problem I am working with here is a **classification problem** as I am predicting whether something is fraud (1) or not fraud (0), based on the input variables in the dataset.

![flowchart](https://user-images.githubusercontent.com/86743951/215003065-f9f9ec31-e39b-4750-bb40-4997e1e2c384.jpg)

### Making correlation

Correlation is a measure of the relationship between two variables. The correlation coefficient ranges from -1 to 1. Below, I've created a bar chart that shows the relationship between the features and the response variable, 'Class'. 

![bar_correlation](https://user-images.githubusercontent.com/86743951/215149758-b0de3e19-a161-4db7-a86e-c51e364813a6.png)


### Working with imbalanced data
With the problem I am working with here, it is important to understand **data imbalance** and how to approach this issue. The credit card fraud detection dataset I am working with have a majority of transactions classified as not being fraud and very few classes as being fraud. 


![countplot](https://user-images.githubusercontent.com/86743951/215146610-a57415ca-7c73-443b-a08f-dce59e622284.png)


Cases that are not fraud (value = 0) make up 99.83% of the dataset while causes that are fraud (value = 1) only make up 0.17%. This is a problem because the objective of many models are to maximize the overall accuracy. However, if one was to measure how good the model is with classification accuracy where it is a percentage of the total correct predictions, they would get a classification score nearing a 100% simply due to the imbalanced nature of the dataset. Steps to minimize bias towards the majority class must be taken and this will be further explored in upcoming posts as I explore various techniques to handle imbalanced data.












