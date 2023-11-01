# ADS-Phase5

In today’s competitive world, it is crucial to understand customer behavior and categorize customers based on their demography and buying behavior.
This is a critical aspect of customer segmentation that allows marketers to better tailor their marketing efforts to various audience subsets in terms of promotional, 
marketing and product development strategies. In this project, execute and apply the scientific approach using k-means clustering algorithm and supermarket mall dataset
are analyzed, the dataset values and parameters provide an organized understanding of the customer buying patterns and behavior base on this study applied model and deploys
dataset segmentation principles using K-Means clustering algorithms. I used python programming language for implementing clustering algorithms. A variety of dataset clusters are
validated based on the calculation of Elbow method and Silhouette Coefficient. In result, identify target customer segment by divide into groups according to common characteristics
and also visualize the four features of customers based on dataset so that the sense can be given to marketing team and plan the strategy accordingly.

Customer segmentation is the process of dividing a customer base into distinct groups or segments based on common characteristics,
such as demographics, behavior, or preferences. 
This allows businesses to tailor their marketing strategies and services to each segment's unique needs and 
preferences.
Dataset:
A dataset is a collection of data, often organized in tabular format, that includes information about customers,
such as demographics, transaction history, or other relevant attributes. In a customer segmentation project, the dataset typically 
includes information about the customers you aim to segment.
Loading Data:
Loading data refers to the process of importing or reading a
dataset into a software environment, such as Python, for analysis. In Python, 
libraries like Pandas are commonly used to load data from
various sources, such as CSV files, Excel sheets, or databases.
Preprocessing:
Data preprocessing involves cleaning, transforming,
and organizing data to make it suitable for analysis.
Common preprocessing tasks include handling missing values,
encoding categorical variables, scaling or normalizing numerical
 features, and removing irrelevant columns.

# **Customer-Segmentation**
# Import our wrangling and visualization library
import pandas as pd
import seaborn as sns
import matplotlib.pyplot as plt
import plotly.express as px
import numpy as np
# Use Case

- Use Case Summary
- Objective Statement:
  * Get business insight about how many product sold every month.
  * Get business insight about how much customer spend their money every month.
  * To reduce risk in deciding where, when, how, and to whom a product, service, or brand will be marketed.
  * To increase marketing efficiency by directing effort specifically toward the designated segment in a manner consistent with that segment’s characteristics.

- Challenges:
  * Large size of data, can not maintain by excel spreadsheet.
  * Need several coordination from each department.
  * Demography data have a lot missing values and typo.

- Methodology / Analytic Technique:
  * Descriptive analysis
  * Graph analysis
  * Segment Analysis

- Business Benefit:
  * Helping Business Development Team to create product differentiation based on the characteristic for each customer.
  * Know how to treat customer with specific criteria.

- Expected Outcome:
  * Know how many product sold every month.
  * Know how much customer spend their money every month.
  * Customer segmentation analysis.
  * Recommendation based on customer segmentation.
  
# Business Understanding

- Retail is the process of selling consumer goods or services to customers through multiple channels of distribution to earn a profit.- This case has some business question using the data:
- How many product sold every month?
- How much customer spend their money every month?
- How about Customer segmentation analysis?
- How about recommendation based on customer segmentation?

# Data Understanding

- Data of Retail Transaction from 01 December 2010 to 09 December 2011
- Source Data: Online retail dataset by UCI Machine Learning Library. 

https://www.kaggle.com/datasets/akram24/mall-customers

- The dataset has 8 columns and 541909 rows.
- Data Dictionary:
- InvoiceNo: Invoice number uniquely assigned to each transaction. 
- StockCode: Product (item) code.
- Description: Product (item) name.
- Quantity: The quantities of each product (item) per transaction. 
- InvoiceDate: The day and time when each transaction was generated.
- UnitPrice: Product price per unit in sterling.
- CustomerID: Customer number uniquely assigned to each customer.
- Country: The name of the country where each customer resides.

# Data preparation 

- Code Used:
- Python Version: 3.7.6
- Packages: Pandas, Numpy, Matplotlib, Seaborn, Sklearn, and Feature Engine 

# Data Cleansing 

- There are about 25% of Null CustomerID in the data. We need to remove them as there is no way we can get the number of CustomerID.
- There are few records with UnitPrice<0 and Quantity<0. We need to remove them from the analysis. This could represent cancelled or returned orders.
- There is more than 90% of 'United Kingdom' customers, therefore we will restrict the data to only United Kingdom customers.

# Modeling Data: K-Means Clustering
- K-Means clustering algorithm is an unsupervised machine learning algorithm that uses multiple iterations to segment the unlabeled data points into K different clusters in a way such that each data point belongs to only a single group that has similar properties.
- K-means gives the best result under the following conditions:
- Data’s distribution is not skewed.
- Data is standardised.
- The data is highly skewed, therefore I will perform log transformations to reduce the skewness of each variable and I standardised the data.
- Finding the optimal number of clusters

# Evaluating Model: K-Means Clustering
- Davies Bouldin Score is a metric for evaluating clustering algorithms. 
- The smaller Davies Bouldin Score is The more optimal the cluster.

# Interpretation of the clusters formed using K-Means
- "Cluster 0" has 29% customers. It belongs to the “Loyal Customer" segment as they Haven’t purchased for some time, but used to purchase frequently (F=2) and spent a lot. 
- "Cluster 1" has 20% customers. It can be interpreted as “Almost Lost". They purchase recently (R=2). However they do not purchase frequently and do not spent a lot. 
- "Cluster 2“ has 30% customers. It can be interpreted as "Lost Cheap Customers". Their last purchase is long ago (R=4), purchased very few (F=4) and spent little (M=4).
- "Cluster 3“has 21% customers. It belongs to the "Best Customers" segment which we saw earlier as they purchase recently (R=1), frequent buyers (F=1), and spent the most (M=1).

# Recommendation
- Recommendation for “Best Customers" segment: Focus on increasing customer purchases therefore it is necessary to form a cross/Up Selling Strategy.
- Recommendation for “Loyal Customers" segment: The business team must optimize the budget campaign and the time campaign for this customer segment in order to maintain their loyalty and increase their value.
- Recommendation for “Almost Lost" segment: This customer segment is very at risk for churn, so focus on activating customers and making repurchases by forming a Reactivation Strategy, Retention Strategy.
- Recommendation for “Lost Cheap Customers" segment: This customer segment has churned, so the focus of the campaign is to reactivate the customer by forming a Reactivation strategy.
