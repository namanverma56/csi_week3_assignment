# Superstore Sales Analytics Project

## 📌 Project Overview
This project focuses on transforming raw, unorganized Superstore sales data into a structured relational database and performing advanced data analysis using SQL. The data was processed inside a Python environment using SQLite to execute relational mapping, analytical subqueries, Common Table Expressions (CTEs), and window functions.

---

## 🛠️ Database Schema & Architecture
The raw data was normalized from a flat file (`superstore_raw`) into three optimized relational tables to eliminate redundancy and improve query performance:

* **`customers`**: Contains unique customer demographic data.
    * `customer_id` (Primary Key), `customer_name`, `segment`
* **`products`**: Contains unique product inventory details.
    * `product_id` (Primary Key), `product_name`, `category`, `sub_category`
* **`orders`**: Contains transactional records mapping purchases back to customers and products.
    * `order_id`, `customer_id` (Foreign Key), `product_id` (Foreign Key), `order_date`, `sales`, `quantity`, `discount`, `profit`

---

## 📊 Analytical Queries Executed

### 1. Advanced SQL Analysis
* **Subqueries:** Isolated high-value individual transactions beating the store-wide sales average and engineered correlated subqueries to find peak customer purchases.
* **CTEs (Common Table Expressions):** Built temporary virtual tables to aggregate complex customer lifetime spending before linking them with master data tables.
* **Window Functions:** Applied `RANK() OVER()` and `ROW_NUMBER() OVER(PARTITION BY ...)` to chronologically sequence user orders and rank overall customer revenue.

### 2. Mini Project: Customer Sales Insights
The system successfully answered critical business intelligence questions directly from the operational tables:
1.  **Top 5 Customers:** Identified the highest revenue-generating accounts for targeted loyalty marketing.
2.  **Bottom 5 Customers:** Flagged low-value accounts for review.
3.  **Single-Order Retention:** Isolated customers who purchased exactly once to identify churn risk.
4.  **Above-Average Spenders:** Filtered core customer segments outperforming average buyer distributions.
5.  **Maximum Order Caps:** Documented the absolute ceiling budget spent per client in a single transaction.

---

## 🚀 Technical Stack
* **Environment:** Google Colab (Python Notebook Notebook wrapper)
* **Language:** SQL (SQLite dialect)
* **Libraries:** `pandas` (for data rendering), `sqlite3` (for database connection engine)
