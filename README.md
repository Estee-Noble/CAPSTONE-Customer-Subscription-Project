CAPSTONE-Customer-Subscription-Project
#### This is where i documented my second main LITA PROJECT on Customer Segmentation for a Subscription service.
---

## Project Title: Customer Segmentation for a Subscription Service.

### Project Overview: This project involves analyzing customer data for a subscription service to identify 
segments,trends and to understand customer behavior, track subscription types,and identify key trends in cancellations and renewals, for interactive Power BI dashboard visualization.
The dataset consists of information such as customer demographics, subscription history, usage patterns, and transaction records. This project highlights my analytical skills in data processing, clustering techniques, and visualization, providing a comprehensive look at how data-driven segmentation can drive business decisions.


### Project Objectives: The primary objective of this project is to segment customers of a subscription service into distinct groups based on shared characteristics and behaviors. By leveraging these insights, the business can better understand customer needs, personalize marketing strategies, and improve customer satisfaction and retention. This segmentation will enable the company to optimize its offerings, increase engagement, and reduce churn, thereby driving long-term growth.


### Scope of Analysis

#### 1. Customer Segmentation:

Group customers based on features like region, subscription type, revenue generated, and whether they canceled.
Identify distinct customer profiles to reveal patterns in subscription preferences, regional engagement differences, and revenue potential by segment.

#### 2. Subscription Lifecycle and Duration Analysis:

Calculate each customer’s subscription duration and examine trends in start and end dates.
Understand how long different customer segments remain active and identify common points in the subscription lifecycle where cancellations occur.

#### 3. Churn and Retention Analysis:

Analyze cancellation patterns to understand the characteristics of customers likely to churn.
Identify potential reasons for cancellations and determine which segments have higher or lower churn rates.

#### 4. Revenue Analysis:

Assess revenue per customer by segment and subscription type to understand the financial contribution of each group.
Identify high-value customers or segments to prioritize for retention and upsell efforts.

### Data definition 
Customer ID: A unique identifee for each customer in the dataset. 
Customer Name: The name of customer associated with each record. 
Region: The geographical location or area where the customer resides or uses the service. 
Subscription Type (Basic, Premium, Standard): The type of subscription plan chosen by the customer, indicating different tiers of service or access.
Subscription Start Date: The date when the customer’s subscription began.
Subscription End Date: The date when the customer’s subscription ended, if applicable.
Cancelled: A field indicating whether the customer has canceled their subscription (True/False).
Revenue: The total revenue generated by the customer over the duration of their subscription.


### Data Collection Approach

#### i. Data Cleaning:

Handle any missing values, correct inconsistencies, and standardize formats (e.g., dates and categorical variables).

Ensure that fields like Subscription Start Date and Subscription End Date are in a consistent date format.

#### ii. Data Processing:

Derive additional features such as Subscription Duration (difference between Subscription Start Date and Subscription End Date).


#### iii. Data Aggregation:

Group data by different categories, such as Region and Subscription Type, to support segmentation and revenue analysis.


### Key Performance Indicators (KPIs)

1. Customer Lifetime Value (CLV):
Average revenue generated by a customer over the duration of their subscription. This is key for understanding segment profitability.

2. Average Subscription Duration:
Calculate the average time customers stay subscribed before cancellation. This metric helps in identifying segments with higher or lower retention.

3. Churn Rate:
Percentage of customers who cancel their subscription within a specific time period. Useful to assess retention strategies for each segment.

4. Revenue per Segment:
Total revenue generated by each segment (e.g., by region or subscription type). Helps in determining the financial impact of each segment.



### Tools for Analysis


1. Data Cleaning and Processing:
Excel: For initial data cleaning, filtering, and preparation.

2. Data Analysis and Visualization:
Power BI: To create interactive dashboards and visualize customer segments, revenue trends, churn analysis, and more.

3. Clustering and Segmentation:
SQL: For creating views and aggregating data by various segments based on criteria such as subscription type, region, or revenue tier.

4. Reporting and Presentation:
Power BI: For generating interactive insights, Creating a detailed report or presentation to demonstrate findings, using data storytelling techniques to make insights actionable.
