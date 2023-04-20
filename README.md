# Predicting Customer Churn 
A Data Science Project

![image](https://user-images.githubusercontent.com/85320743/222021144-43a219c7-5dab-41f0-8cbb-6d6fff60be99.png)


## Objective
To build a supervised machine learning model that accurately predicts wether a customer from a telecommunication company will churn or not and to identify the key metrics that impact this decision. 

## Business Problem
A multinational telecommunication company wants to know why customers are churning in hopes of   reducing the churn rate therby increasing company growth which in turn will increase revenue and profits. 

In order for company growth to take place the churn rate, the percentage of subcribers who discontinue their subscriptions to a business within a given time period, has to be lower than the rate of new customers subscribing to the business.


### Seudo Steps

1. Load in data

2. Clean data

3. Exploratory Data Analysis

4. Feature engineer

5. Model Creation & Optimization

6. Interpret Results & Give Recommendations

### Load in Data

The purpose of this project is to learn and practice my ability to use data and machine learning to solve common marketing/business problems. With this in mind, the data won't be coming from a real client, instead from this [GitHub repository](https://github.com/PacktPublishing/Data-Science-for-Marketing-Analytics-Second-Edition) in the form of a csv file.

The data has 4,708 customers and 15 columns, one being the target variable. 

<img width="1083" alt="Screenshot 2023-04-20 124016" src="https://user-images.githubusercontent.com/85320743/233471327-bac76da8-36b1-4055-8b4b-e1cc378b32ac.png">


### Cleaning Data

#### Dealing with Null Values

This dataset is relatively free of null values, as seen below. Columns "Complaint Code" and "Condition of Current Handset" are the only columns with null values. 

<img width="474" alt="Screenshot 2023-04-20 123851" src="https://user-images.githubusercontent.com/85320743/233471628-d70f158c-e382-462c-b00c-b125fb6b5dcd.png">

In both cases, null values will be filled in with the mode of their respective column. This is the best choice because in each instance the most common values are the over whelming majority of occurances in the data. Deleting the row or the column would not be the efficient in these cases because there are not enough nulls to warrant deleting the column and there are to many nulls to warrant deleting the rows without significantly reducing the size of the data.

<img width="728" alt="Screenshot 2023-04-20 130244" src="https://user-images.githubusercontent.com/85320743/233475539-7d7a8e30-3c3e-43e9-8143-09bf49aecb11.png">







