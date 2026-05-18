# Commercial Performance & Profitability Analytics

An end-to-end Business Intelligence project built using SQL and Power BI to analyze revenue performance, profitability trends, customer behavior, regional contribution, and operational efficiency across global markets.

The goal of this project was not only to track sales performance, but to identify the business factors affecting profitability and operational decision-making.

---

# Business Problem

Businesses often focus heavily on revenue growth without fully understanding whether that growth translates into sustainable profitability.

This project analyzes how factors such as discounts, customer demographics, product categories, regional sales performance, and sales representative efficiency impact overall business profitability.

The analysis was performed using SQL for data querying and KPI generation, followed by Power BI for dashboard development and business visualization.

---

# Project Objectives

- Analyze revenue and profit performance across countries
- Identify high-performing and low-performing product categories
- Measure the impact of discount strategies on profitability
- Evaluate customer purchasing behavior across demographics
- Compare sales representative performance
- Track monthly revenue trends and operational KPIs
- Generate business recommendations based on analytical findings

---

# Tools & Technologies

| Tool | Purpose |
|---|---|
| SQL (PostgreSQL) | Data analysis & querying |
| Power BI | Dashboard development |
| DAX | KPI calculations |
| Window Functions | Ranking & trend analysis |
| CTEs | Complex analytical queries |
| Data Modeling | Relationship management |

---

# Dataset Overview

The dataset contains transactional sales data including:

- Orders
- Revenue
- Profit
- Product categories
- Discounts
- Customer demographics
- Countries
- Sales representatives
- Payment methods
- Monthly sales trends

---

# Key Business Metrics

| Metric | Value |
|---|---|
| Total Revenue | $4.21M |
| Total Profit | $959.3K |
| Profit Margin | 22.8% |
| Total Orders | 3K |
| Average Order Value | $1.40K |

---

# SQL Analysis Performed

The SQL workflow focused on transforming raw transactional data into business insights.

### Data Validation & Cleaning
- Null value detection
- Duplicate record checks
- Data consistency validation

### KPI Analysis
- Revenue calculations
- Profit calculations
- Profit margin calculations
- Average order value analysis

### Advanced SQL Analysis
- Country-wise contribution analysis
- Product category profitability analysis
- Discount impact analysis
- Monthly revenue trend analysis
- Sales representative ranking
- Running revenue totals
- Top-performing product analysis

---

# SQL Concepts Used

- Aggregate Functions
- GROUP BY
- ORDER BY
- CASE Statements
- Window Functions
- RANK()
- SUM() OVER()
- Common Table Expressions (CTEs)

---
# Sample SQL Queries
```
## Sales Representative Ranking
SELECT 
    sales_rep,
    ROUND(SUM(revenue), 2) AS total_revenue,
    RANK() OVER(
        ORDER BY SUM(revenue) DESC
    ) AS revenue_rank
FROM global_retail_sales
GROUP BY sales_rep;

## Running Revenue Trend
SELECT 
    order_month,
    monthly_revenue,
    SUM(monthly_revenue) OVER(
        ORDER BY order_month
    ) AS running_revenue
FROM (
    SELECT 
        DATE_TRUNC('month', order_date) AS order_month,
        SUM(revenue) AS monthly_revenue
    FROM global_retail_sales
    GROUP BY order_month
) revenue_trend;
```
## Dashboard Features
- The Power BI dashboard includes:
- Revenue & Profit KPI Cards
- Country-wise Performance Analysis
- Product Category Analysis
- Customer Demographic Insights
- Payment Method Analysis
- Sales Representative Ranking
- Monthly Revenue Trends
- Profitability Analysis

## Key Insights
- The UK generated the highest revenue contribution.
- The US achieved the strongest profitability performance.
- Home & Kitchen was the highest-performing category.
- Higher discount levels reduced average profitability.
- Customer demographics showed different purchasing patterns across age groups and genders.
- Some sales representatives generated strong revenue but weaker profit contribution.


## Dashboard Preview
Overview Dashboard
<img width="1300" height="711" alt="Executive overview" src="https://github.com/user-attachments/assets/604cb48f-2561-4278-9c49-080bc52e1216" />

Customer Behavior
<img width="1277" height="712" alt="Customer Behavior" src="https://github.com/user-attachments/assets/f91cb0d4-d095-4c07-8179-8cb8b50bfa07" />

Sales Performance
<img width="1285" height="705" alt="Sales Reps and Regional" src="https://github.com/user-attachments/assets/f946d108-318a-445f-a253-c55a574840ef" />


