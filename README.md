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


#### Dealing with data types

The columns "Condition_of_Current_Handset" and "Current_TechSupComplaints" are categorical data so they will be converted from float64 and int64 to an object data type. 

<img width="738" alt="Screenshot 2023-04-20 133400" src="https://user-images.githubusercontent.com/85320743/233481631-007a767f-e714-435d-b585-9280cf1a1cb8.png">

#### Rename columns and drop redundant column

Rename columns to have a standard syntax, blank spaces will be replaced with an underscore. 

The column "Target_Churn" is redundant as it desribes the same information as "Target_Code", which is the target variable of this model. To protect our model from any data leakage, the column must be dropped from the dataset as it would give the model information it otherwise would not know in practice at the time you'd want to use the model to make a prediction. 

<img width="507" alt="Screenshot 2023-04-20 134817" src="https://user-images.githubusercontent.com/85320743/233484309-1371660c-2661-4340-82ef-90edcf99328c.png">

### Exploratory Data Analysis

<img width="871" alt="Screenshot 2023-04-20 140854" src="https://user-images.githubusercontent.com/85320743/233488146-20bc3c26-f3a2-4c78-ba9a-ddf00ecbcfea.png">

The average current bill amount is $19,819.65 and the average account age is 26 months (2 years). The average amount of calls is 9,271, but the average increases if we only consider calls during the weekday. 

The average amount of days an account is delinquent is 14 days, with a min and max ranging from 0 to 126 days. 

#### Average Metrics for Customers who Churned 

0 = Not Churned
1 = Churned

<img width="817" alt="image" src="https://user-images.githubusercontent.com/85320743/233489437-87337fa7-54b4-4aca-b89e-21f5ec74e37e.png">

- Average current bill: $20,176
- Average number of calls per month: 9,354
- Average account age: 25 Months
- Average number of days with delinquent account: 19 Days

#### Correlation Heatmap

<img width="820" alt="Screenshot 2023-04-20 144944" src="https://user-images.githubusercontent.com/85320743/233495070-586b295d-a5b1-496f-a3e8-559a9af2beff.png">

The heatmap above shows the column "Avg_Days_Delinquent" having a moderate postitive correlation to the target variable, which is the highest compared to all other independent features.

#### Univariate Analysis

<img width="930" alt="Screenshot 2023-04-20 150327" src="https://user-images.githubusercontent.com/85320743/233497097-251625f4-f900-4178-be7f-3852a4bea34f.png">



#### Bivariate Analysis

<img width="723" alt="Screenshot 2023-04-20 153137" src="https://user-images.githubusercontent.com/85320743/233501158-aea00294-d6d0-413a-9469-90aefb7767d7.png">

Customers who churn most commonly complain about a billing problem followed by call quality.

<img width="650" alt="Screenshot 2023-04-20 153148" src="https://user-images.githubusercontent.com/85320743/233501288-57876623-1e5f-4343-9660-5ff84fe76e98.png">

More silver plan customers churn compared to gold plan customers.

<img width="942" alt="Screenshot 2023-04-20 153333" src="https://user-images.githubusercontent.com/85320743/233501676-e5633c8b-a098-4c79-8b0a-d447745b6fcc.png">


