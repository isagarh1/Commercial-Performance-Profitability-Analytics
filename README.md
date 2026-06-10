# Commercial Performance & Profitability Drivers Analysis

An end-to-end Business Intelligence project built using SQL and Power BI to analyze revenue performance, profitability drivers, discount effectiveness, regional contribution, category performance, and sales representative efficiency. across global markets.

The goal of this project was not only to track sales performance, but to identify the business factors affecting profitability and operational decision-making.

---

# Business Problem

Businesses often focus heavily on revenue growth without fully understanding whether that growth translates into sustainable profitability.

This project investigates how discounts, product categories, regional performance, and sales representative effectiveness influence overall profitability and commercial performance.

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
- Executive KPI Overview
- Monthly Revenue Trend Analysis
- Country Performance Analysis
- Category Profitability Analysis
- Discount Impact Analysis
- Sales Representative Efficiency Analysis
- Profitability Driver Analysis

## Key Insights
- The UK generated the highest revenue contribution.
- The US achieved the highest profit margin.
- Home & Kitchen generated the highest total profit.
- Higher discount levels were associated with lower profit margins.
- Significant profitability differences existed across sales representatives.
- Sales representative efficiency had a greater impact on profitability than demographic factors.

## Business Recommendations
### 1. Optimize Discount Strategy
- Higher discount levels were associated with lower profit margins.
- The business should reduce excessive discounting and implement targeted promotions to improve profitability while maintaining sales performance.
### 2. Strengthen Sales Performance Management
- Significant differences were observed in profit margin and profit per transaction across sales representatives. 
- Performance evaluation should incorporate profitability-based KPIs alongside revenue targets to encourage sustainable sales growth.
### 3. Prioritize High-Profit Product Categories
- Product categories contributing the highest overall profit should receive greater focus in inventory planning, marketing campaigns, and growth initiatives to maximize business returns.
### 4. Focus on Profitable Market Expansion
- While some countries generated higher revenue, others achieved stronger profit margins. 
- Future expansion strategies should balance revenue growth with profitability performance to ensure long-term commercial success.
### 5. Implement Profitability-Focused Monitoring
- Business performance should be monitored using Revenue, Profit Margin, Discount Levels, and Profit per Transaction together rather than relying solely on revenue growth. 
- This provides a more comprehensive view of commercial performance and supports better decision-making.


## Dashboard Preview
Executive Overview
<img width="1307" height="722" alt="Excecutive Overview" src="https://github.com/user-attachments/assets/4c058e64-47b4-45d8-97d3-c63851b9692e" />

Profitability Drivers Analytics
<img width="1310" height="723" alt="Profitability drivers" src="https://github.com/user-attachments/assets/c55e5d97-2b25-439b-a5df-69ffd9c5bb76" />
 





