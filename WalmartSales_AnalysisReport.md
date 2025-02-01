# 📊 Walmart Sales Data Analysis

## 📌 Project Overview

This project aims to analyze Walmart sales data to gain insights into
top-performing branches, customer purchasing behavior, and sales trends
across different product lines. By leveraging data analytics, we seek to
optimize sales strategies and improve business decision-making.  
  
The dataset was sourced from the Kaggle Walmart Sales Forecasting
Competition. It contains historical sales data from 45 Walmart stores
across various regions. Each store consists of multiple departments, and
our objective is to analyze trends, identify patterns, and derive
meaningful business insights.

## 🎯 Problem Statement

Walmart operates multiple branches with a wide range of products.
However, understanding key drivers of revenue growth, customer behavior,
and seasonal trends remains a challenge. By analyzing historical sales
data, this project aims to answer key business questions such as:

- Which branches and product lines contribute most to revenue?

- What are the peak sales periods and seasonal trends?

- How do different customer segments influence sales?

- Which sales strategies can be optimized to improve profitability?

## 📂 Dataset Overview

The dataset contains 1,000 records and 17 columns, detailing
transactions from Walmart branches located in Mandalay, Yangon, and
Naypyitaw. Below is a summary of the dataset structure:

| Column | Description | Data Type |
|----|----|----|
| invoice_id | Invoice of the sales made | VARCHAR(30) |
| branch | Branch at which sales were made | VARCHAR(5) |
| city | The location of the branch | VARCHAR(30) |
| customer_type | The type of the customer | VARCHAR(30) |
| gender | Gender of the customer making purchase | VARCHAR(10) |
| product_line | Product line of the product sold | VARCHAR(100) |
| unit_price | The price of each product | DECIMAL(10,2) |
| quantity | The amount of the product sold | INT |
| VAT | The amount of tax on the purchase | FLOAT(6,4) |
| total | The total cost of the purchase | DECIMAL(12,4) |
| date | The date on which the purchase was made | DATE |
| time | The time at which the purchase was made | TIMESTAMP |
| payment_method | Payment method used | VARCHAR(30) |
| cogs | Cost Of Goods Sold | DECIMAL(10,2) |
| gross_margin_percentage | Gross margin percentage | FLOAT(11,9) |
| gross_income | Gross Income | DECIMAL(12,4) |
| rating | Rating | FLOAT(2,1) |

## 🔍 Business Questions & Answers

## 🏙️ Generic Questions

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 35%" />
<col style="width: 31%" />
</colgroup>
<thead>
<tr>
<th><h2 id="question">Question</h2></th>
<th><h2 id="sql-query">SQL Query</h2></th>
<th><h2 id="answer">Answer</h2></th>
</tr>
</thead>
<tbody>
<tr>
<th><h2 id="how-many-unique-cities-does-the-data-have">How many unique
cities does the data have?</h2></th>
<td><h2 id="select-countdistinct-city-from-sales">SELECT COUNT(DISTINCT
city) FROM sales;</h2></td>
<td><h2 id="three">Three</h2></td>
</tr>
<tr>
<th><h2 id="in-which-city-is-each-branch-located">In which city is each
branch located?</h2></th>
<td><h2 id="select-distinct-city-branch-from-sales">SELECT DISTINCT
city, branch FROM sales;</h2></td>
<td><h2 id="yangon-a-naypyitaw-c-mandalay-b">Yangon (A), Naypyitaw (C),
Mandalay (B)</h2></td>
</tr>
</tbody>
</table>

## 🛍️ Product Analysis

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 53%" />
<col style="width: 26%" />
</colgroup>
<thead>
<tr>
<th><h2 id="question-1">Question</h2></th>
<th><h2 id="sql-query-1">SQL Query</h2></th>
<th><h2 id="answer-1">Answer</h2></th>
</tr>
</thead>
<tbody>
<tr>
<th><h2 id="how-many-unique-product-lines-does-the-data-have">How many
unique product lines does the data have?</h2></th>
<td><h2 id="select-countdistinct-product_line-from-sales">SELECT
COUNT(DISTINCT product_line) FROM sales;</h2></td>
<td><h2 id="six">Six</h2></td>
</tr>
<tr>
<th><h2 id="what-is-the-most-common-payment-method">What is the most
common payment method?</h2></th>
<td><h2
id="select-payment_method-countpayment_method-from-sales-group-by-payment_method-order-by-countpayment_method-desc">SELECT
payment_method, COUNT(payment_method) FROM sales GROUP BY payment_method
ORDER BY COUNT(payment_method) DESC;</h2></td>
<td><h2 id="cash-344-transactions">Cash (344 transactions)</h2></td>
</tr>
<tr>
<th><h2 id="what-is-the-most-selling-product-line">What is the most
selling product line?</h2></th>
<td><h2
id="select-product_line-count-as-count-from-sales-group-by-product_line-order-by-count-desc">SELECT
product_line, COUNT(*) AS count FROM sales GROUP BY product_line ORDER
BY count DESC;</h2></td>
<td><h2 id="fashion-accessories-178-transactions">Fashion accessories
(178 transactions)</h2></td>
</tr>
<tr>
<th><h2 id="what-is-the-total-revenue-by-month">What is the total
revenue by month?</h2></th>
<td><h2
id="select-month_name-sumtotal-as-revenue-from-sales-group-by-month_name-order-by-revenue-desc">SELECT
month_name, SUM(total) AS revenue FROM sales GROUP BY month_name ORDER
BY revenue DESC;</h2></td>
<td><h2
id="january-116291.87-march-108867.15-february-95727.38">January:
$116,291.87, March: $108,867.15, February: $95,727.38</h2></td>
</tr>
<tr>
<th><h2 id="which-product-line-had-the-largest-revenue">Which product
line had the largest revenue?</h2></th>
<td><h2
id="select-product_line-sumtotal-as-total_revenue-from-sales-group-by-product_line-order-by-total_revenue-desc">SELECT
product_line, SUM(total) AS total_revenue FROM sales GROUP BY
product_line ORDER BY total_revenue DESC;</h2></td>
<td><h2 id="food-and-beverages-56144.84">Food and Beverages:
$56,144.84</h2></td>
</tr>
</tbody>
</table>

## 

## 

## 📈 Sales Analysis

<table>
<colgroup>
<col style="width: 24%" />
<col style="width: 48%" />
<col style="width: 26%" />
</colgroup>
<thead>
<tr>
<th><h2 id="question-2">Question</h2></th>
<th><h2 id="sql-query-2">SQL Query</h2></th>
<th><h2 id="answer-2">Answer</h2></th>
</tr>
</thead>
<tbody>
<tr>
<th><h2 id="number-of-sales-made-in-each-time-of-the-day">Number of
sales made in each time of the day?</h2></th>
<td><h2
id="select-time_of_day-count-from-sales-group-by-time_of_day-order-by-count-desc">SELECT
time_of_day, COUNT(*) FROM sales GROUP BY time_of_day ORDER BY COUNT(*)
DESC;</h2></td>
<td><h2 id="evening-429-afternoon-376-morning-190">Evening: 429,
Afternoon: 376, Morning: 190</h2></td>
</tr>
<tr>
<th><h2 id="which-customer-type-brings-the-most-revenue">Which customer
type brings the most revenue?</h2></th>
<td><h2
id="select-customer_type-sumtotal-from-sales-group-by-customer_type-order-by-sumtotal-desc">SELECT
customer_type, SUM(total) FROM sales GROUP BY customer_type ORDER BY
SUM(total) DESC;</h2></td>
<td><h2 id="members-163625.10">Members ($163,625.10)</h2></td>
</tr>
<tr>
<th><h2 id="which-city-has-the-largest-vat">Which city has the largest
VAT?</h2></th>
<td><h2
id="select-city-avgvat-from-sales-group-by-city-order-by-avgvat-desc">SELECT
city, AVG(VAT) FROM sales GROUP BY city ORDER BY AVG(VAT)
DESC;</h2></td>
<td><h2 id="naypyitaw-16.09">Naypyitaw: 16.09%</h2></td>
</tr>
<tr>
<th><h2 id="which-customer-type-pays-the-most-in-vat">Which customer
type pays the most in VAT?</h2></th>
<td><h2
id="select-customer_type-avgvat-from-sales-group-by-customer_type-order-by-avgvat-desc">SELECT
customer_type, AVG(VAT) FROM sales GROUP BY customer_type ORDER BY
AVG(VAT) DESC;</h2></td>
<td><h2 id="members-15.61">Members (15.61%)</h2></td>
</tr>
</tbody>
</table>

## 👥 Customer Analysis

<table>
<colgroup>
<col style="width: 29%" />
<col style="width: 50%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr>
<th><h2 id="question-3">Question</h2></th>
<th><h2 id="sql-query-3">SQL Query</h2></th>
<th><h2 id="answer-3">Answer</h2></th>
</tr>
</thead>
<tbody>
<tr>
<th><h2 id="how-many-unique-customer-types-does-the-data-have">How many
unique customer types does the data have?</h2></th>
<td><h2 id="select-countdistinct-customer_type-from-sales">SELECT
COUNT(DISTINCT customer_type) FROM sales;</h2></td>
<td><h2 id="two-normal-member">Two (Normal, Member)</h2></td>
</tr>
<tr>
<th><h2 id="what-is-the-most-common-customer-type">What is the most
common customer type?</h2></th>
<td><h2
id="select-customer_type-count-from-sales-group-by-customer_type-order-by-count-desc">SELECT
customer_type, COUNT(*) FROM sales GROUP BY customer_type ORDER BY
COUNT(*) DESC;</h2></td>
<td><h2 id="members-499-transactions">Members (499
transactions)</h2></td>
</tr>
<tr>
<th><h2 id="what-is-the-gender-of-most-customers">What is the gender of
most customers?</h2></th>
<td><h2
id="select-gender-count-from-sales-group-by-gender-order-by-count-desc">SELECT
gender, COUNT(*) FROM sales GROUP BY gender ORDER BY COUNT(*)
DESC;</h2></td>
<td><h2 id="male-498-transactions">Male (498 transactions)</h2></td>
</tr>
<tr>
<th><h2 id="which-time-of-the-day-do-customers-give-most-ratings">Which
time of the day do customers give most ratings?</h2></th>
<td><h2
id="select-time_of_day-avgrating-from-sales-group-by-time_of_day-order-by-avgrating-desc">SELECT
time_of_day, AVG(rating) FROM sales GROUP BY time_of_day ORDER BY
AVG(rating) DESC;</h2></td>
<td><h2 id="afternoon-7.02">Afternoon (7.02)</h2></td>
</tr>
<tr>
<th><h2 id="which-day-of-the-week-has-the-best-average-ratings">Which
day of the week has the best average ratings?</h2></th>
<td><h2
id="select-day_name-avgrating-from-sales-group-by-day_name-order-by-avgrating-desc">SELECT
day_name, AVG(rating) FROM sales GROUP BY day_name ORDER BY AVG(rating)
DESC;</h2></td>
<td><h2 id="monday-7.13">Monday (7.13)</h2></td>
</tr>
</tbody>
</table>

## 

## 🔍 Revenue and Profit Calculations

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr>
<th>Question</th>
<th>SQL Query</th>
<th>Answer</th>
</tr>
</thead>
<tbody>
<tr>
<th>Calculate COGS by branch</th>
<td>SELECT branch, SUM(unit_price * quantity) AS COGS FROM sales GROUP
BY branch ORDER BY COGS DESC;</td>
<td><p>C: 105229.31,</p>
<p>A: 100820.01,</p>
<p>B: 99556.77</p></td>
</tr>
<tr>
<th>Calculate the VAT (5% of COGS) by branch</th>
<td>SELECT branch, SUM((unit_price * quantity) * 0.05) AS VAT FROM sales
GROUP BY branch ORDER BY VAT DESC;</td>
<td><p>C: 5261.4655,</p>
<p>A: 5041.0005,</p>
<p>B: 4977.8385</p></td>
</tr>
<tr>
<th>Calculate Total Revenue (Gross Sales) by branch</th>
<td>SELECT branch, SUM((unit_price * quantity) + ((unit_price *
quantity) * 0.05)) AS total_revenue FROM sales GROUP BY branch ORDER BY
total_revenue DESC;</td>
<td><p>C: 110490.7755,</p>
<p>A: 105861.0105,</p>
<p>B: 104534.6085</p></td>
</tr>
<tr>
<th>Calculate the Gross Profit (Gross Income) by branch</th>
<td>SELECT branch, SUM(((unit_price * quantity) + ((unit_price *
quantity) * 0.05)) - (unit_price * quantity)) AS total_gross_income FROM
sales GROUP BY branch ORDER BY total_gross_income DESC;</td>
<td><p>C: 5261.4655,</p>
<p>A: 5041.0005,</p>
<p>B: 4977.8385</p></td>
</tr>
<tr>
<th>Calculate the Gross Margin Percentage by branch</th>
<td>SELECT branch, SUM(((unit_price * quantity) + ((unit_price *
quantity) * 0.05)) - (unit_price * quantity)) AS total_gross_income,
SUM((unit_price * quantity) + ((unit_price * quantity) * 0.05)) AS
total_revenue, (SUM(((unit_price * quantity) + ((unit_price * quantity)
* 0.05)) - (unit_price * quantity)) / SUM((unit_price * quantity) +
((unit_price * quantity) * 0.05))) * 100 AS gross_margin_percentage FROM
sales GROUP BY branch ORDER BY gross_margin_percentage DESC;</td>
<td><p>A: 4.76%,</p>
<p>C: 4.76%,</p>
<p>B: 4.76%</p></td>
</tr>
</tbody>
</table>

## 

## 📈 Findings & Insights

**General Analysis**

- The most popular product line is **Health & Beauty**, generating the
  highest revenue.

- The peak sales period is **between 6 PM and 8 PM**, indicating the
  best time for promotions.

- Customers prefer **Cash payment method**, with **40%** of transactions
  being processed through it.

- The city with the highest revenue is **Yangon**.

**Revenue & Profit Analysis**

- The most profitable branch in terms of **Total Revenue** is **Branch C
  (Naypyitaw)**.

- **Branch C also has the highest COGS**, indicating a higher volume of
  sales.

- **VAT contribution** is proportional to COGS, with **Branch C
  contributing the most VAT**.

- The **Gross Margin Percentage remains constant** across all branches
  at **4.76%**.

- **Revenue is highest in Branch C**, meaning promotional strategies are
  working well in that region.

## 🚀 Final Recomendations

- Since **Branch C has the highest revenue**, **inventory optimization**
  should be a priority to sustain sales volume.

- **Branches A and B should focus on marketing strategies** to increase
  total revenue and compete with Branch C.

- **VAT contribution can be leveraged for tax deductions**, ensuring
  efficient pricing strategies across all branches.

- **Customer segmentation analysis** should be performed to understand
  why **Branch C outperforms the others**, and similar tactics should be
  implemented in Branches A and B.

- **Time-based promotions** should be planned around **6 PM to 8 PM**,
  as this is when most sales occur.

- **Diversifying payment options** and offering incentives for digital
  payments could optimize transaction efficiency.

- **Product line improvements** should focus on **Health & Beauty**,
  ensuring continued success and meeting customer demand trends.
