# AtliQ Hardware Sales Insights Dashboard

An interactive *Tableau dashboard* built to analyze the sales performance of AtliQ Hardware — a fictional company — and derive actionable insights for improving revenue and product strategy.

---

## Overview

This project aims to simulate a real-world business intelligence task where sales data is analyzed to:

- Track monthly and quarterly sales trends
- Evaluate performance by region and product category
- Identify underperforming areas
- Support data-driven strategic decisions for sales growth

---

## Tools & Technologies

- *SQL*: Data extraction and transformation
- *Tableau*: Dashboard creation and visualization
- *Spreadsheet (Excel)*: Light data preparation and structure verification

---

## Key Features

- *Region-wise Sales Performance*: Compare revenue contributions across locations
- *Sales Trend Analysis*: Monitor sales over time using line charts and heatmaps
- *Product Line Breakdown*: Visualize sales by category and product SKU
- *Dynamic Filters*: Slice data by region, time, and product to uncover insights
- *KPI Cards*: Highlight Total Revenue, Units Sold, and Sales Growth %

---

## Screenshots

![image](https://github.com/user-attachments/assets/536de2be-62a4-4f2c-b4ad-92309892254f)
![image](https://github.com/user-attachments/assets/13aaa072-32d4-431a-aef9-56cd2f19ac24)



---

## Project Workflow

1. *Data Cleaning (Excel/SQL)*  
   - Removed duplicates, validated dates, and ensured consistency in naming conventions

2. *Data Modeling (SQL)*  
   - Joined product, region, and sales datasets using keys  
   - Filtered out invalid entries and created calculated fields like Discounted Price

3. *Dashboard Creation (Tableau)*  
   - Designed a responsive, user-friendly layout  
   - Used bar charts, line graphs, filters, and parameter controls to enhance interactivity  
   - Calculated growth metrics using Tableau formulas

---

## Outcomes

- Revealed that North and East regions underperformed in Q3  
- Identified product categories with high returns and low profit margins  
- Suggested marketing focus on top-selling regions and bundling offers for underperforming SKUs  
- Estimated a potential *7% revenue increase* from proposed optimizations

---

## How to Use

1. Clone the repository  
2. Open the .twb or .twbx file in *Tableau Desktop*  
3. Interact with filters and visualizations to explore insights


Data Analysis Using SQL


1.Show all customer records

    SELECT * FROM customers;

2.Show total number of customers

    SELECT count(*) FROM customers;

3.Show transactions for Chennai market (market code for chennai is Mark001

    SELECT * FROM transactions where market_code='Mark001';

4.Show distrinct product codes that were sold in chennai

    SELECT distinct product_code FROM transactions where market_code='Mark001';

5.Show transactions where currency is US dollars

    SELECT * from transactions where currency="USD"

6.Show transactions in 2020 join by date table

    SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;

7.Show total revenue in year 2020,

    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and 
    transactions.currency="INR\r" or transactions.currency="USD\r";

8.Show total revenue in year 2020, January Month,

    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and 
    date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");

9.Show total revenue in year 2020 in Chennai

    SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and 
    transactions.market_code="Mark001";
