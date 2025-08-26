# 🍕 Pizza Sales Power BI Dashboard

## 📌 Project Overview

This project presents an **interactive Pizza Sales Dashboard** built in
**Power BI**.\
The goal is to analyze sales performance, customer behavior, and product
trends to uncover insights that can help improve business decisions.

------------------------------------------------------------------------

## 📊 Features & KPIs

The dashboard provides a comprehensive set of **Key Performance
Indicators (KPIs):**

-   ✅ **Total Revenue**\
-   ✅ **Total Orders**\
-   ✅ **Total Pizzas Sold**\
-   ✅ **Average Order Value (AOV)**\
-   ✅ **Top-Selling Pizza Categories & Sizes**\
-   ✅ **Daily / Monthly Sales Trends**\
-   ✅ **Best Performing Days & Hours**\
-   ✅ **Revenue Contribution by Category**\
-   ✅ **Customer Purchase Behavior**\
-   ✅ **Delivery vs. Dine-in Performance**

------------------------------------------------------------------------

## 📂 Dataset

The dataset contains pizza sales transactions with details such as:

-   `order_id` → Unique order identifier\
-   `order_date` → Date of order\
-   `pizza_id` → Pizza identifier\
-   `pizza_category` → Category (Classic, Supreme, Veggie, etc.)\
-   `pizza_size` → Size of pizza\
-   `quantity` → Number of pizzas ordered\
-   `price` → Price per pizza

------------------------------------------------------------------------

## 🛠 Tools & Technologies

-   **Power BI Desktop** -- Data visualization and dashboard creation\
-   **DAX** -- For calculated measures and KPIs\
-   **Excel / CSV** -- Source dataset\
-   **SQL SERVER** -- TO query the required data

------------------------------------------------------------------------

## 📷 Dashboard Preview

*(Add screenshots)*

------------------------------------------------------------------------

## 📈 Sample DAX Measures

``` dax
-- Total Revenue
Total Revenue = SUM('pizza_sales'[total_price])

-- Total Orders
Total Orders = DISTINCTCOUNT('pizza_sales'[order_id])

-- Average Order Value (AOV)
Average Order Value = [Total Revenue] / [Total Orders]

-- Total Pizzas Sold
Total Pizzas Sold = SUM('pizza_sales'[quantity])

-- Daily Average Revenue
Daily Avg Revenue = AVERAGEX(VALUES('pizza_sales'[order_date]), [Total Revenue])
```

------------------------------------------------------------------------

## 🗄️ SQL Queries  

```sql
-- Total Revenue
SELECT SUM(TotalPrice) AS TotalRevenue
FROM Sales;

-- Total Orders
SELECT COUNT(DISTINCT OrderID) AS TotalOrders
FROM Sales;

-- Total Quantity Sold
SELECT SUM(Quantity) AS TotalQuantity
FROM Sales;

-- Average Order Value
SELECT 
    SUM(TotalPrice) / COUNT(DISTINCT OrderID) AS AverageOrderValue
FROM Sales;

-- Best Selling Pizza
SELECT TOP 1 PizzaName, SUM(Quantity) AS TotalQuantity
FROM Sales
GROUP BY PizzaName
ORDER BY SUM(Quantity) DESC;

-- Worst Selling Pizza
SELECT TOP 1 PizzaName, SUM(Quantity) AS TotalQuantity
FROM Sales
GROUP BY PizzaName
ORDER BY SUM(Quantity) ASC;

------------------------------------------------------------------------

## 🚀 Insights Gained

-   The **Classic Pizza Category** contributes the highest revenue.\
-   **Large-sized pizzas** are the most popular among customers.\
-   Peak sales occur during **weekends and evenings**.\
-   The business heavily relies on **few best-selling pizzas**,
    suggesting a need to diversify promotions.

------------------------------------------------------------------------

## 📌 How to Use

1.  Clone or download the repository.\
2.  Open the `.pbix` file in **Power BI Desktop**.\
3.  Refresh the data (if source file is available).\
4.  Explore the dashboard interactively.

------------------------------------------------------------------------

## 📧 Contact

For any questions or collaboration:\
**Author:** Joseph Villarin
