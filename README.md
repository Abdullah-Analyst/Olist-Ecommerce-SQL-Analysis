# 📊 E-Commerce Sales Analytics Using SQL

## 📌 Project Overview

This project analyzes the **Olist Brazilian E-Commerce Dataset** using SQL to generate actionable business insights related to customers, orders, products, sellers, payments, and revenue performance.

The objective of this project is to demonstrate practical SQL skills commonly used in real-world **Data Analyst**, **Business Analyst**, and **Business Intelligence** roles. The analysis focuses on transforming raw transactional data into meaningful insights that support data-driven decision-making.

The dataset contains real-world e-commerce transactions from a Brazilian online marketplace, including customer information, order details, products, sellers, and payment records.

---

## 🎯 Business Objectives

This project aims to answer the following business questions:

* How many customers, orders, products, and sellers exist in the marketplace?
* What is the distribution of order statuses?
* How have orders changed over time?
* Which product categories generate the highest sales volume?
* Which categories generate the highest revenue?
* What payment methods are most frequently used?
* What is the average order value?
* Which customer cities contribute the most revenue?
* Which customer cities place the highest number of orders?
* Which sellers generate the highest revenue?
* Which seller cities contribute the most sales?
* How does revenue change month-over-month?

---

## 📂 Dataset Information

**Dataset:** Olist Brazilian E-Commerce Public Dataset

### Tables Used

| Table       | Description                               |
| ----------- | ----------------------------------------- |
| customers   | Customer details and location information |
| orders      | Order records and purchase timestamps     |
| order_items | Products included in each order           |
| payments    | Payment transactions and values           |
| products    | Product information and categories        |
| sellers     | Seller information and locations          |
| categories  | Product category translations             |

---

## 🛠 SQL Skills Demonstrated

This project demonstrates the following SQL concepts:

* SELECT Statements
* Aggregate Functions

  * COUNT()
  * SUM()
  * AVG()
* GROUP BY
* ORDER BY
* INNER JOIN
* Multi-Table Joins
* Common Table Expressions (CTEs)
* Window Functions

  * RANK()
  * LAG()
* Date Functions
* Revenue Analysis
* Customer Analytics
* Seller Performance Analysis
* Time-Series Analysis

---

## 📈 Key Analyses Performed

### 1. Marketplace Overview

* Total Customers
* Total Orders
* Total Products
* Total Sellers

### 2. Order Analysis

* Order Status Distribution
* Monthly Order Trends

### 3. Revenue Analysis

* Monthly Revenue Trend
* Month-over-Month Revenue Growth (%)

### 4. Product Analysis

* Top Product Categories by Orders
* Top Categories by Revenue
* Best Selling Products

### 5. Customer Analysis

* Top Customer Cities by Number of Orders
* Top Customer Cities by Revenue

### 6. Seller Analysis

* Top Performing Sellers
* Top Seller Cities by Revenue

### 7. Payment Analysis

* Payment Method Distribution
* Average Order Value

### 8. Advanced SQL Analysis

* Product Category Revenue Ranking using Window Functions

---

## 🔍 Key Insights

The analysis revealed several important business insights:

* Delivered orders account for the vast majority of marketplace transactions, indicating strong order fulfillment performance.
* Revenue and order volumes fluctuate significantly across different months.
* A small number of product categories generate a disproportionately large share of total marketplace revenue.
* Customer purchasing activity is concentrated in a few major cities.
* Credit card payments represent the most frequently used payment method.
* Seller performance varies significantly across different regions.
* Top-performing sellers contribute a substantial portion of marketplace revenue.
* Product category rankings highlight clear revenue leaders and growth opportunities.

---

## 💻 Sample SQL Query

### Monthly Revenue Trend

```sql
SELECT
    strftime('%Y-%m', o.order_purchase_timestamp) AS month,
    ROUND(SUM(p.payment_value), 2) AS revenue
FROM orders o
JOIN payments p
    ON o.order_id = p.order_id
GROUP BY month
ORDER BY month;
```

### Revenue Growth Using Window Functions

```sql
WITH MonthlyRevenue AS (
    SELECT
        strftime('%Y-%m', o.order_purchase_timestamp) AS Month,
        ROUND(SUM(p.payment_value),2) AS Revenue
    FROM orders o
    JOIN payments p
        ON o.order_id = p.order_id
    GROUP BY Month
)

SELECT
    Month,
    Revenue,
    ROUND(
        ((Revenue - LAG(Revenue) OVER (ORDER BY Month))
        / LAG(Revenue) OVER (ORDER BY Month)) * 100,
        2
    ) AS Growth_Percentage
FROM MonthlyRevenue;
```

---

## 📸 Project Screenshots

The project includes screenshots of:

* Order Status Analysis
* Monthly Order Trend
* Monthly Revenue Trend
* Monthly Revenue Growth (%)
* Payment Method Analysis
* Top Product Categories
* Top Categories by Revenue
* Top Customer Cities by Number of Orders
* Top Customer Cities by Revenue
* Top Products by Units Sold
* Best Selling Products
* Top Sellers
* Top Seller Cities

---

## 🧰 Tools Used

* SQL
* SQLite
* DB Browser for SQLite
* Microsoft Excel
* GitHub

---

## 📁 Project Structure

```text
Olist-Ecommerce-SQL-Analysis
│
├── README.md
├── ecommerce_sales_analysis.sql
├── project_report.pdf
│
└── screenshots/
    ├── order_status_analysis.png
    ├── monthly_orders_trend.png
    ├── monthly_revenue_trend.png
    ├── monthly_revenue_growth.png
    ├── payment_method_analysis.png
    ├── top_product_categories.png
    ├── top_categories_by_revenue.png
    ├── top_customer_cities_by_orders.png
    ├── top_customer_cities_by_revenue.png
    ├── top_products_by_units_sold.png
    ├── best_selling_products.png
    ├── top_sellers.png
    └── top_seller_cities.png
```

---

## 🎯 Portfolio Value

This project demonstrates end-to-end SQL analytics capabilities using a real-world e-commerce dataset.

It showcases skills in:

* Data Exploration
* KPI Reporting
* Customer Analysis
* Seller Performance Evaluation
* Revenue Analysis
* Business Intelligence Reporting
* Advanced SQL Techniques

The work reflects practical analytical tasks commonly performed by:

* Data Analysts
* Business Analysts
* Reporting Analysts
* Business Intelligence Analysts
* SQL Developers

---

## 👨‍💻 Author

**Abdullah**

**Data Analyst | SQL | Excel | Power BI | Business Intelligence**

Feel free to connect with me on LinkedIn and explore my portfolio projects.
