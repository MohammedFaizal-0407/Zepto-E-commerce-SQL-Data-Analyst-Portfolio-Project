# ⚡ Zepto E-Commerce — SQL Data Analyst Portfolio Project

A comprehensive SQL-based data analysis project simulating a real-world **quick-commerce analytics** use case inspired by **Zepto** — India's leading 10-minute grocery delivery platform. This project covers database design, data exploration, and business problem-solving across sales, inventory, customers, and delivery operations.

---

## 📂 Repository Structure

```
Zepto-SQL-Project/
│
├── datasets/
│   ├── customers.csv
│   ├── products.csv
│   ├── orders.csv
│   ├── order_items.csv
│   ├── deliveries.csv
│   └── inventory.csv
│
├── schema/
│   └── zepto_schema.sql        -- Table creation & relationships
│
├── queries/
│   ├── 01_data_exploration.sql
│   ├── 02_sales_analysis.sql
│   ├── 03_customer_analysis.sql
│   ├── 04_product_analysis.sql
│   ├── 05_delivery_analysis.sql
│   └── 06_advanced_queries.sql
│
└── README.md
```

---

## 🗃️ Database Schema

### Tables & Key Columns

| Table | Key Columns |
|-------|------------|
| `customers` | customer_id, name, city, signup_date, loyalty_tier |
| `products` | product_id, name, category, sub_category, price, weight_grams |
| `orders` | order_id, customer_id, order_date, order_time, total_amount, payment_method, status |
| `order_items` | order_item_id, order_id, product_id, quantity, unit_price, discount |
| `deliveries` | delivery_id, order_id, dark_store_id, assigned_time, delivered_time, delivery_minutes, delivery_status |
| `inventory` | inventory_id, product_id, dark_store_id, stock_quantity, reorder_level, last_restocked |

---

## ❓ Business Problems Solved

### 🔎 Data Exploration
1. What is the total number of customers, orders, and products in the database?
2. What are the distinct product categories and sub-categories available?
3. List all orders placed in the last 30 days with their status
4. Identify and handle NULL or missing values across all tables

### 📈 Sales Analysis
5. What is the total revenue generated month-over-month?
6. Which month recorded the highest and lowest sales?
7. What is the average order value (AOV) by city and payment method?
8. Which product categories contribute the most to overall revenue?
9. What is the revenue split between discounted vs. non-discounted orders?
10. Identify the top 10 best-selling products by quantity and by revenue

### 👥 Customer Analysis
11. How many new customers were acquired each month?
12. What is the repeat purchase rate — customers who ordered more than once?
13. Identify the top 10 highest-spending customers
14. What is the customer distribution across loyalty tiers (Silver / Gold / Platinum)?
15. Which cities have the highest number of active customers?
16. What is the average time between a customer's first and second order?
17. Segment customers using RFM analysis (Recency, Frequency, Monetary)

### 📦 Product Analysis
18. Which products are most frequently bought together (market basket pairs)?
19. What is the average discount given per product category?
20. Identify products with zero sales in the last 60 days (dead stock)
21. Which sub-categories have the highest return/cancellation rate?
22. What is the price distribution across product categories?

### 🚴 Delivery Analysis
23. What is the average delivery time overall and by dark store?
24. What percentage of orders were delivered within 10 minutes?
25. Which dark stores have the highest on-time delivery rate?
26. Identify peak order hours and their impact on delivery time
27. How many orders were delayed (delivered after 20 minutes)?

### 🧠 Advanced Queries
28. Rank customers by total spend using window functions (`RANK`, `DENSE_RANK`)
29. Calculate a 7-day rolling average of daily revenue
30. Find the month-over-month growth rate in orders using `LAG()`
31. Identify customers at risk of churning (no order in the last 45 days)
32. Build a cohort table showing retention by monthly signup cohort

---

## 🛠️ SQL Concepts Used

| Concept | Applied In |
|---------|-----------|
| `JOINs` (INNER, LEFT, SELF) | Customer-order linking, product-category joins |
| `CTEs` & Subqueries | Multi-step aggregations, RFM analysis |
| Window Functions (`RANK`, `ROW_NUMBER`, `LAG`, `LEAD`) | Customer ranking, MoM growth, rolling averages |
| `CASE` Statements | Order status bucketing, loyalty segmentation |
| Aggregate Functions (`SUM`, `COUNT`, `AVG`) | Revenue, AOV, delivery metrics |
| `GROUP BY` + `HAVING` | Filtered aggregations |
| Date Functions (`DATEDIFF`, `DATEPART`, `FORMAT`) | Cohort analysis, delivery time calculations |
| String Functions (`CONCAT`, `TRIM`, `UPPER`) | Data cleaning and formatting |

---

## 💡 Key Business Insights

- 🕙 **Peak ordering hours** fall between 7–9 AM and 6–9 PM, correlating with longer delivery times due to high demand on dark stores
- 🛒 **Fruits & Vegetables** and **Dairy** categories drive the highest order frequency, while **Personal Care** drives the highest average order value
- 👤 **Top 10% of customers** account for over 40% of total revenue — highlighting the importance of loyalty program investment
- 📦 **~18% of SKUs** recorded zero sales in the last 60 days, indicating dead stock that strains dark store capacity
- 🚴 **Dark stores in metro cities** achieve sub-10-minute delivery for 72% of orders vs. 54% in Tier 2 cities
- 🔄 **Repeat purchase rate** stands at 63%, with Gold and Platinum tier customers ordering 3x more frequently than Silver tier

---

## 🚀 How to Run

1. Set up a SQL Server / PostgreSQL / MySQL instance
2. Run `zepto_schema.sql` to create all tables
3. Import the CSV files from the `datasets/` folder into the respective tables
4. Execute query files in order from `01_` to `06_`

```sql
-- Quick start: verify data load
SELECT COUNT(*) FROM orders;
SELECT COUNT(*) FROM customers;
SELECT COUNT(*) FROM products;
```

---

## 👤 Author

**Mohammed Faizal** — Data Analyst

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/mhd-faizal0407)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=flat&logo=github&logoColor=white)](https://github.com/MohammedFaizal-0407)
