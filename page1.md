--- 
title: "Problem Statement, Stakeholders, and Data Collection Methods"
date: 2023-01-20
layout: default
rank: 1
---

## A Classification Problem: Credit Card Fraud Detection

![credit_cards](https://user-images.githubusercontent.com/86743951/218533716-2fb72f6c-9847-438a-91ab-fced9d3cf217.jpg)

### Problem Statement
In this digital era, credit card usage is higher than it has ever been. [Statista](https://www.statista.com/statistics/568523/preferred-payment-methods-usa/) found that in 2021, 40% of all transactions were made with a credit card. It is a common form of theft where criminals will make purchases or obtain cash advances in the cardhoder's name, leaving the cardholder or the credit card company with the bill. As credit card usage grows, the risk of fraud grows as well. 

Key findings by [dataprot](https://dataprot.net/statistics/credit-card-fraud-statistics/) include:
- People in their 30s are the most vulnerable to credit card fraud.
- 54% of businesses are “somewhat confident” they would be able to detect fraudulent activity on time.
- By 2023, retailers will lose about $130 billion each year on card-not-present transactions.
- The amount of credit card data available on the dark web increased by 135% last year.
- Card-not-present fraud is now 81% more common than point-of-sale fraud.
- 87% of surveyed adults in the US admit to shopping online over public WiFi.


### Stakeholders

The stakeholders include the credit card companies and the credit card users. Credit card companies are invested in making sure that customers are not charged for items that they did not purchase, because doing so would lead to mistrust in its usage, consequently costing the company money.

Consumers are also stakeholders in this problem. Consumers want to stay protected in the purchases that they make which can not only cause monetary loss but also emotional distress. It has been found that 83% of Americans own at least one credit card and the average American has 3.8 credit cards ([Zippia](https://www.zippia.com/advice/credit-card-statistics/#:~:text=83%25%20of%20Americans%20own%20at,American%20has%203.8%20credit%20cards.)). 


### Data Source
I will be using the dataset from [Kaggle](https://www.kaggle.com/datasets/mlg-ulb/creditcardfraud) which has been collected and analyzed during a research collaboration between Worldline and the [Machine Learning Group](https://mlg.ulb.ac.be/wordpress/). The dataset includes transactions made by credit cards in September 2013 by European cardholders. Due to confidentiality, the dataset contains only numerical input variables (V1, V2,..., V28) as a result of a PCA transformation.
