# 📊 Customer Churn Prediction SQL Analysis

## 🚀 Project Overview

This project focuses on analyzing customer churn behavior using SQL.  
The dataset simulates a telecom/customer subscription business and includes:

- Customer information
- Support ticket activity
- Marketing campaign responses

The project demonstrates end-to-end SQL analytics skills including:

- Data Exploration
- Joins
- Aggregations
- CASE Statements
- Subqueries
- CTEs
- Window Functions
- Business Logic Analysis

---

# 🗂️ Database Schema

## 1️⃣ Customers Table

| Column | Description |
|---|---|
| customer_id | Unique customer ID |
| gender | Customer gender |
| tenure | Subscription duration |
| contract_type | Contract category |
| monthly_charges | Monthly subscription charge |
| churn | Customer churn status |

---

## 2️⃣ Support_Tickets Table

| Column | Description |
|---|---|
| ticket_id | Unique ticket ID |
| customer_id | Customer reference |
| issue_type | Support issue category |
| resolution_time | Time taken to resolve |
| satisfaction_score | Customer satisfaction rating |

---

## 3️⃣ Marketing_Campaign Table

| Column | Description |
|---|---|
| campaign_id | Unique campaign ID |
| customer_id | Customer reference |
| campaign_type | Campaign channel |
| response | Customer response |

---

# ⚡ SQL Concepts Covered

## ✅ Basic SQL
- SELECT
- WHERE
- ORDER BY
- GROUP BY
- HAVING
- Aggregate Functions

## ✅ Joins
- INNER JOIN
- LEFT JOIN
- Multi-table Joins

## ✅ Aggregations
- SUM()
- AVG()
- COUNT()
- ROUND()

## ✅ CASE Statements
- Customer Segmentation
- Churn Categorization
- Satisfaction Labeling

## ✅ Subqueries
- Correlated Subqueries
- Nested Queries
- Average Comparison Logic

## ✅ CTEs
- Revenue Summaries
- Churn Calculations
- Support Reports
- Customer Risk Analysis

## ✅ Window Functions
- RANK()
- ROW_NUMBER()
- LAG()
- Running Totals

---

# 📈 Key Business Analysis

## 🔥 Customer Analytics
- Identify churned customers
- Detect high-risk customers
- Segment customers by value

## 💰 Revenue Analytics
- Customer lifetime value
- Revenue by contract type
- Running revenue calculations

## 🎫 Support Analytics
- Resolution time analysis
- Satisfaction score tracking
- Ticket trend analysis

## 📢 Marketing Analytics
- Campaign response analysis
- Churn reduction effectiveness
- Engagement tracking

---

# 🧠 Example SQL Queries

## Churn Percentage Using CTE

```sql
WITH churn_percentage AS (

    SELECT 
        COUNT(*) AS total_customers,

        SUM(
            CASE
                WHEN churn = 1 THEN 1
                ELSE 0
            END
        ) AS churn_customers

    FROM Customers
)

SELECT 
    total_customers,
    churn_customers,

    ROUND(
        churn_customers * 100.0 / total_customers,
    2) AS churn_percent

FROM churn_percentage;
