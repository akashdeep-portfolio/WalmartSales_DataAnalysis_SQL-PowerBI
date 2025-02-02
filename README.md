![Sample Image](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRztL0WzSHxYdzc8FmFZ8pCYA8GxsAThVhioAoQIrfPmnM2527iMnLvRXyd_5VO1xYdRg&usqp=CAU)


# Walmart Sales Data Analysis
## Project Overview
This project aims to analyze Walmart sales data to gain insights into top-performing branches, customer purchasing behavior, and sales trends across different product lines. By leveraging data analytics, we seek to optimize sales strategies and improve business decision-making.

The dataset was sourced from the Kaggle Walmart Sales Forecasting Competition. It contains historical sales data from 45 Walmart stores across various regions. Each store consists of multiple departments, and our objective is to analyze trends, identify patterns, and derive meaningful business insights.


## Problem Statement
Walmart operates multiple branches with a wide range of products. However, understanding key drivers of revenue growth, customer behavior, and seasonal trends remains a challenge. By analyzing historical sales data, this project aims to answer key business questions such as:

•	Which branches and product lines contribute most to revenue?

•	What are the peak sales periods and seasonal trends?

•	How do different customer segments influence sales?

•	Which sales strategies can be optimized to improve profitability?


## Dataset Overview
The dataset was obtained from the [Kaggle Walmart Sales Forecasting Competition](https://www.kaggle.com/c/walmart-recruiting-store-sales-forecasting). The dataset contains 1,000 records and 17 columns, detailing transactions from Walmart branches located in Mandalay, Yangon, and Naypyitaw. Below is a summary of the dataset structure:

| Column            | Description                                   | Data Type        |
|-------------------|-----------------------------------------------|------------------|
| invoice_id        | Invoice of the sales made                     | VARCHAR(30)      |
| branch            | Branch at which sales were made               | VARCHAR(5)       |
| city              | The location of the branch                    | VARCHAR(30)      |
| customer_type     | The type of the customer                      | VARCHAR(30)      |
| gender            | Gender of the customer making purchase        | VARCHAR(10)      |
| product_line      | Product line of the product sold              | VARCHAR(100)     |
| unit_price        | The price of each product                     | DECIMAL(10, 2)   |
| quantity          | The amount of the product sold                | INT              |
| VAT               | The amount of tax on the purchase             | FLOAT(6, 4)      |
| total             | The total cost of the purchase                | DECIMAL(12, 4)   |
| date              | The date on which the purchase was made       | DATETIME         |
| time              | The time at which the purchase was made       | TIMESTAMP        |
| payment           | The total amount paid                         | DECIMAL(30)      |
| cogs              | Cost Of Goods sold                            | DECIMAL(10, 2)   |
| gross_margin_pct  | Gross margin percentage                       | FLOAT(11, 9)     |
| gross_income      | Gross Income                                  | DECIMAL(12, 4)   |
| rating            | Rating                                        | FLOAT(2, 1)      |


## Analysis List:

1.	Product Analysis

> Conduct analysis on the data to understand the different product lines, the products lines performing best and the product lines that need to be improved.

2.	Sales Analysis
   
> This analysis aims to answer the question of the sales trends of product. The result of this can help use measure the effectiveness of each sales strategy the business applies and what modificatoins are needed to gain more sales.

3.	Customer Analysis

> This analysis aims to uncover the different customers segments, purchase trends and the profitability of each customer segment.

## Approach Used
***1.	Data Wrangling***

During this initial phase, the data is examined to detect any NULL or missing values, and strategies for data replacement are implemented to address and substitute these values effectively.
- Build a database
- Create a table and insert the data.
- Select columns with null values in them. Null values are not present in our database because, in creating the tables, NOT NULL was specified for each field, effectively filtering out any null values.

***2.	Feature Engineering***

This will help use generate some new columns from existing ones.
- Add a new column named time_of_day to give insight of sales in the Morning, Afternoon and Evening. This will help answer the question on which part of the day most sales are made.
- Add a new column named day_name that contains the extracted days of the week on which the given transaction took place (Mon, Tue, Wed, Thur, Fri). This will help answer the question on which week of the day each branch is busiest.
- Add a new column named month_name that contains the extracted months of the year on which the given transaction took place (Jan, Feb, Mar). Help determine which month of the year has the most sales and profit.

***3.  Exploratory Data Analysis (EDA)***

Conducting exploratory data analysis is essential to address the project's listed questions and objectives.

## Business Questions to Answer

### Generic Questions
1. How many unique cities does the data have?
2. In which city is each branch?

### Product Analysis
1. How many unique product lines does the data have?
2. What is the most common payment method?
3. What is the most selling product line?
4. What is the total revenue by month?
5. What month had the largest COGS?
6. What product line had the largest revenue?
5. What is the city with the largest revenue?
6. What product line had the largest VAT?
7. Fetch each product line and add a column to those product line showing "Good", "Bad". Good if its greater than average sales
8. Which branch sold more products than average product sold?
9. What is the most common product line by gender?
12. What is the average rating of each product line?

### Sales Analysis
1. Number of sales made in each time of the day per weekday
2. Which of the customer types brings the most revenue?
3. Which city has the largest tax percent/ VAT (**Value Added Tax**)?
4. Which customer type pays the most in VAT?

### Customer Analysis
1. How many unique customer types does the data have?
2. How many unique payment methods does the data have?
3. What is the most common customer type?
4. Which customer type buys the most?
5. What is the gender of most of the customers?
6. What is the gender distribution per branch?
7. Which time of the day do customers give most ratings?
8. Which time of the day do customers give most ratings per branch?
9. Which day fo the week has the best avg ratings?
10. Which day of the week has the best average ratings per branch?

## Revenue And Profit Calculations
1. What is the total Cost of Goods Sold (COGS) for each branch?
2. How much VAT (5% of COGS) does each branch contribute?
3. What is the total revenue (gross sales) generated by each branch?
4. What is the Gross Profit (Gross Income) by each branch?
5. What is the Gross Margin Percentage for each branch?
