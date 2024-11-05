# CAPSTONE-Customer-Subscription-Project
#### This is where i documented my second main LITA PROJECT on Customer Segmentation for a Subscription service.

---


## Project Title: Customer Segmentation for a Subscription Service.

### Project Overview: 
#### This project involves analyzing customer data for a subscription service to identify segments,trends and to understand customer behavior, track subscription types,and identify key trends in cancellations and renewals, for interactive Power BI dashboard visualization.
The dataset consists of information such as customer demographics, subscription history, usage patterns, and transaction records. This project highlights my analytical skills in data processing, clustering techniques, and visualization, providing a comprehensive look at how data-driven segmentation can drive business decisions.


### Project Objectives: 
#### The primary objective of this project is to segment customers of a subscription service into distinct groups based on shared characteristics and behaviors. By leveraging these insights, the business can better understand customer needs, personalize marketing strategies, and improve customer satisfaction and retention. This segmentation will enable the company to optimize its offerings, increase engagement, and reduce churn, thereby driving long-term growth.


### Data Collected 
#### The following are the datasets found in the column:

-  **Customer ID**: A unique identifer for each customer in the dataset. 
Customer Name: The name of customer associated with each record. 
-  **Region**: The geographical location or area where the customer resides or uses the service. 
-  **Subscription Type (Basic, Premium, Standard)**: The type of subscription plan chosen by the customer, indicating different tiers of service or access.
Subscription Start Date: The date when the customer’s subscription began.
Subscription End Date: The date when the customer’s subscription ended, if applicable.
-  **Cancelled**: A field indicating whether the customer has canceled their subscription (True/False).
-  **Revenue**: The total revenue generated by the customer over the duration of their subscription.


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





### Tools for Analysis

-  **Microsoft Excel** [Download Here]

i.  Data Cleaning and Processing: Used for initial data cleaning, handling missing variables,filtering, and preparation.

ii.  Data analysis: Excel helps to provides powerful features like Pivot Tables for quick aggregations and analysis, making it a go-to tool for many analysts.


 
-  **Power BI**: 
Visualization To create interactive dashboards and visualize customer segments, revenue trends, churn analysis, and more.

-  **SQL**:
i.  Clustering and Segmentation: For creating aggregating data and sorting queries by various segments based on criteria such as subscription type, region, or revenue tier.

-  **Power BI**: 
Reporting and Presentation: For generating interactive insights, Creating a detailed report or presentation to demonstrate findings, using data storytelling techniques to make insights actionable.


EXPLORATION DATA ANALYSIS (WITH EXCEL)
-  Pivot tables to analyze subscription patterns.



-  Average subscription duration 




-  Most popular subscription types.


EXPLORATION DATA ANALYSIS (WITH SQL)

#### Retrieve the total number of customers from each region.

```SQL
COUNT [CustomerID] AS TotalCustomers select * FROM LITA_CapstoneCustomerDATA
GROUP By Region
```


#### Most popular subscription type by the number of customers.
```SQL
SELECT SubscriptionType, COUNT(CustomerID) AS TotalCustomers
```

#### Customers who canceled their subscription within 6 months.

```SQL
select * FROM CustomerData
Group By SubscriptionType
SELECT CustomerID, CustomerName, SubscriptionStart, SubscriptionEnd
select* FROM CustomerData
WHERE Canceled = 'TRUE'
AND DATEDIFF(day, SubscriptionEnd, SubscriptionStart) <=180;
```

#### Calculate the average subscription duration for all customers.

```SQL
SELECT AVG(DATEDIFF(month, SubscriptionEnd, SubscriptionStart)) AS AvgSubscriptionDuration
select * From CustomerData
SELECT CustomerID, CustomerName, SubscriptionStart, SubscriptionEnd
```

#### Customers with subscriptions longer than 12 months.
```SQL
select * FROM CustomerData
WHERE DATEDIFF(day, SubscriptionEnd, SubscriptionStart) >365;
```

#### Total revenue by subscription type.
```SQL
Select subscriptiontype, sum(revenue) AS TotalRevenue
select * From CustomerData
GROUP By SubscriptionType
```

#### Top 3 regions by subscription cancellations.
```SQL
Select TOP 3 region, count(subscriptionend) AS cancellations
select * From CustomerData
WHERE subscriptionend IS NOT NULL
Group By region 
```

#### Find the total number of active and canceled subscriptions.
```SQL
SELECT Canceled, COUNT(CustomerID) AS TotalSubscriptions
select * From CustomerData

GROUP By Canceled
```

EXPLORATION DATA ANALYSIS (WITH POWER BI)

This dashboard visualizes: 

-  Key customer segments
 

-  Cancellations


-  Subscription trends



SELECT Region, COUNT(CustomerID) AS TotalCustomers
select * FROM CustomerData
GROUP By Region

SELECT SubscriptionType, COUNT(CustomerID) AS TotalCustomers

select * FROM CustomerData

Group By SubscriptionType

SELECT CustomerID, CustomerName, SubscriptionStart, SubscriptionEnd

select* FROM CustomerData

WHERE Canceled = 'TRUE'

AND DATEDIFF(day, SubscriptionEnd, SubscriptionStart) <=180;

SELECT AVG(DATEDIFF(month, SubscriptionEnd, SubscriptionStart)) AS AvgSubscriptionDuration

select * From CustomerData

SELECT CustomerID, CustomerName, SubscriptionStart, SubscriptionEnd

select * FROM CustomerData

WHERE DATEDIFF(day, SubscriptionEnd, SubscriptionStart) >365;

Select subscriptiontype, sum(revenue) AS TotalRevenue

select * From CustomerData

GROUP By SubscriptionType

Select TOP 3 region, count(subscriptionend) AS cancellations

select * From CustomerData

WHERE subscriptionend IS NOT NULL

Group By region 

SELECT Canceled, COUNT(CustomerID) AS TotalSubscriptions

select * From CustomerData

GROUP By Canceled
------Retrieve the total sales for each product category-----
SELECT Product, SUM(Quantity * UnitPrice) AS Total_Sales
select * FROM SalesData
GROUP By Product

-----Find the number of sales transactions in each region-----
SELECT Region, COUNT(*) AS Total_Sales_Value
select *FROM SalesData
GROUP By Region

------Find the highest-selling product by total sales value----
SELECT TOP 1 Product, Sum(Quantity * UnitPrice) AS Total_Sales_Value
select * FROM SalesData
GROUP By Product
ORDER By Total_Sales_Value DESC

-------Calculate total revenue per product-----
SELECT Product, Sum(Quantity * UnitPrice) as Total_Revenue
select *FROM SalesData
GROUP By Product
ORDER By 2 DESC

------Calculate monthly sales totals for the current year----
SELECT OrderDate As Monthly_Sales_Total, Sum(Quantity * UnitPrice) AS Monthly_Sales_Total
select * FROM SalesData
WHERE OrderDate LIKE '2024'
GROUP By OrderDate

-----Find the top 5 customers by total purchase amount-----
SELECT TOP 5 Customer_Id, Sum(Quantity * UnitPrice) AS Total_Purchase_Amount
select * FROM SalesData
GROUP By Customer_Id
ORDER By 2 DESC

------Calculate the percentage of total sales contributed by each region----
SELECT Region,
	Round((Sum(Quantity * UnitPrice) / (SELECT SUM(CAST(Quantity * UnitPrice AS FLOAT)) FROM SalesData) * 100), 1) AS Percentage_Of_Total_Sales
select * FROM SalesData
GROUP By Region
