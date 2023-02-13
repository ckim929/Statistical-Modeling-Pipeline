--- 
title: "Data Cleaning and Exploratory Data Analysis (EDA)"
date: 2023-01-25
layout: default
rank: 2
---

## Data Cleaning
The first step of the data science pipeline is data cleaning. **Data cleaning** is the process of fixing or removing incorrect, duplicate, or incomplete data within a dataset. The dataset I am working with contains only numerical variables resulting from a principal component analysis (PCA) transformation.

Upon initial analysis, the data I am working with here is relatively clean. I've checked for null and duplicate values using **data.isnull().sum()** and **data.duplicated()**. I removed the duplicage values found in the dataset. All of the features are numerical variables labeled **V1, V2,..., V28**. However, because data cleaning is an iterative process it may be possible that I have to come back to this step again.

## Exploratory Data Analysis (EDA)
It's important to understand the data to gather as much insight as possible from it. This step is all about making sense of the data by looking for patterns, spotting anomalies, and checking assumptions through summary statistics and visualizations ([towardsdatascience](https://towardsdatascience.com/exploratory-data-analysis-8fc1cb20fd15)). 

![EDA](https://user-images.githubusercontent.com/86743951/218554426-a54bcb7d-68b8-4a77-951d-d02ce1a76642.png)

After reading in the data, I used the *.shape* function of the pandas library to return the shape of the dataframe. We can see that there are 284807 rows and 31 columns. 

![datashape](https://user-images.githubusercontent.com/86743951/215136138-7f1a73b0-2ce0-4473-a3be-2157d6bf219f.png)

I then used the *.head()* function of the pandas library to look at the first five observations of my dataset. athe function is useful for getting a quick glance to see if my dataset encompasses the right type of data.

![head](https://user-images.githubusercontent.com/86743951/214944882-7877bba7-3458-4de6-8bd7-3e98fd4761cb.png)


The *.info()* function is also useful pandas function for printing important information such as its index dtype and columns, non-null values and memory usage.

![datainfo](https://user-images.githubusercontent.com/86743951/215006655-682f7a9b-632b-4d45-895e-bbef744514e1.png)


Next, I used the *is.null().sum()* function of the pandas library to see if there existed any null values in the dataset. 

![null_values](https://user-images.githubusercontent.com/86743951/215003746-1351832a-c590-4fb7-b0e0-723957f149c6.png)

The dataset does not contain any null values.

I also used the *.duplicated()* to see if there existed any duplicate rows in my dataset. The *.duplicated()* function of the pandas library returns a boolean series denoting duplicate rows. 

![duplicates](https://user-images.githubusercontent.com/86743951/215144874-93d46864-71d0-40a3-ad48-e42dd7f54fac.png)

I found that my dataset contains 1081 duplicated rows. 

I dropped the duplicated rows using the pandas drop_duplicates() function.

![drop_duplicates](https://user-images.githubusercontent.com/86743951/215145698-ac4c8bfd-4eff-4def-aee9-c8dcf5c436eb.png)


### Making correlation

Correlation is a measure of the relationship between two variables. The correlation coefficient ranges from -1 to 1, where -1 decribes a perfect negative correlation and +1 describes a perfect positive (direct) correlation. 

Below, I've created a bar chart that shows the relationship between the features and the response variable, 'Class', from order of least correlated to most correlated. 

![bar_correlation](https://user-images.githubusercontent.com/86743951/215149758-b0de3e19-a161-4db7-a86e-c51e364813a6.png)


### Working with imbalanced data
With the problem that I am working with here, it is important to understand **data imbalance** and how to approach this issue. The credit card fraud detection dataset I am working with have a majority of transactions classified as not being fraudulent and *very* few classes as being fraud. 


![countplot](https://user-images.githubusercontent.com/86743951/215146610-a57415ca-7c73-443b-a08f-dce59e622284.png)


Cases that are not fraud (value = 0) make up 99.83% of the dataset while causes that are fraud (value = 1) only make up 0.17%. This is a problem because the objective of many models is to maximize the overall accuracy. However, if one was to measure how good the model is with classification accuracy where it is a percentage of the total correct predictions, they would get a classification score nearing a 100% simply due to the imbalanced nature of the dataset. Steps to minimize bias towards the majority class must be taken and this will be further explored in upcoming posts as I explore various techniques to handle imbalanced data.











