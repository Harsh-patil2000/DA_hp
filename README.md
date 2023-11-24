# Olist Store Analysis

### Table of Contents
- [Project Overview](#project-Overview)
- [Data Sources](#Data-Sources)
- [Tools](#tools)
- [Data Cleaning/Preparation](#Data-Cleaning/Preparation)
- [Data Analysis](#Data-Analysis)
- [Results](#Results)
- [Recommendations](#Recommendations)
- [Limitations](#Limitations)

### Project Overview
  This data analysis project aims tp provide insights into the sales performance of an store company over the past year.
  By analyzing various aspects of the sales data,we seek to identify trends,make data-driven recommendations, and gain a deeper understanding of the company's performance.

### Data Sources 
The data source contains mainly 9 csv files with customer data as well as store data mainly customers,geolocation,order items,payments,reviews,orders,products,sellers, and category name translation.

### Tools

- Excel - Data Cleaning
- Power BI - Creating a report
   -[Click here to see the report]()
- Tableau - Creating a report
   -[Click here to see the report]()
- MySQL - Data Analysis
### Data Cleaning/Preparation
In the initial data preparation phase, we performed the following tasks:
1. Data Loading and inspection.
2. Handling missing values.
3. Data Cleaning and formatting

### Data Analysis 
Include some interesting code/features worked with
``` sql
select pmt.payment_type,count(pmt.order_id) as Total_Orders from olist_order_payments_dataset as pmt join 
(select distinct ord.order_id,rw.review_score from olist_orders_dataset as ord 
join olist_order_reviews_dataset_copy rw on ord.order_id=rw.order_id where review_score=5) as rw5
on pmt.order_id=rw5.order_id group by pmt.payment_type order by Total_Orders desc;
```
### Results 
The analysis results are summarized as follows:
1.The maximum number of orders placed with review score 5 is of payment type credit card and least is from debit card.
2.The sales are more during Weekdays as compared to Weekends in Olist Superstore.
3.Sao Paulo city has the maximum payment values of all the cities in the given dataset with average payment value 136 and price 108.
4.The number of shipping days has an inversely proportional relationship with the review score.

### Recommendations
1.The store can give payback options in debit cards so that customers are motivated to use this mode of payment for their purchases.
2.The store can adopt certain strategies to retain the sales during weekdays by giving special offers.
3.Other cities should take sales insights from Sao Paulo and use similar strategies to increase their Sales in a similar fashion.


### Limitations
I had to remove the values which contain  special characters like ?,$ as it was creating a confusion during analysis and,
also it was not possible to replace them as the major part of them was missing.


