# 🍕 Pizza Sales Dashboard

An interactive Power BI dashboard project that provides deep insights into pizza sales, using **SQL** for backend data processing and **Power BI** for dynamic visualization. The dashboard highlights key business metrics such as revenue, trends, best/worst sellers, and category performance to support data-driven decisions.

---

## 📊 Project Overview

This project analyzes a fictional pizza sales dataset to uncover insights into order patterns, sales distribution, and performance by product type. It includes two main dashboards:

### 🏠 Home Dashboard
- **KPIs**:
  - Total Revenue
  - Average Order Value
  - Average Pizzas per Order
  - Total Pizzas Sold
  - Total Orders
- **Trends**:
  - Daily Order Trends (Day of Week)
  - Monthly Order Trends
- **Sales Analysis**:
  - Sales by Pizza Category (Classic, Veggie, Chicken, Supreme)
  - Sales by Pizza Size (S, M, L, XL, XXL)
- **Filters**:
  - Date Range Selector
  - Category Dropdown
- **Navigation**:
  - Sidebar to switch between dashboards

### ⭐ Best/Worst Sales Dashboard
- **Best Sellers**:
  - Top 5 Pizzas by Revenue
  - Top 5 by Quantity
  - Top 5 by Order Count
- **Worst Sellers**:
  - Bottom 5 Pizzas by Revenue
  - Bottom 5 by Quantity
  - Bottom 5 by Order Count

---

## 🧠 Key Insights

- **Busiest Days**: Friday and Saturday evenings
- **Peak Months**: July and January
- **Top Performer**:  
  - 💰 Thai Chicken Pizza (by revenue)  
  - 🍕 Classic Deluxe (by quantity/orders)
- **Lowest Performer**: Brie Carre Pizza

---

## 🛠️ Tools & Technologies

- **📈 Power BI** – For building interactive dashboards and visuals  
- **🛢️ SQL (MySQL)** – For backend data aggregation and metrics  
- **📂 CSV Files** – As the raw data source  
- **📊 DAX** – For calculated columns and dynamic filtering

---

## 🧮 Sample SQL Queries

```sql
-- Total Revenue
SELECT SUM(total_price) AS Total_Revenue FROM pizza_sales;

-- Average Order Value
SELECT SUM(total_price) / COUNT(DISTINCT order_id) AS Avg_Order_Value FROM pizza_sales;

-- Percentage of Sales by Category
SELECT pizza_category,
       ROUND(SUM(quantity) * 100.0 / (SELECT SUM(quantity) FROM pizza_sales), 2) AS percentage_share
FROM pizza_sales
GROUP BY pizza_category;
