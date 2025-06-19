# blinkit_Data_Analysis

# 🛒 Blinkit Sales Data Analysis (SQL Project)

This project contains SQL queries used to analyze **Blinkit retail sales data**, including total sales, average ratings, item types, outlet types, and more.

---

## 📁 Database Used

```sql
USE blinkit;
```
##📊 Key Metrics & Insights
###1. Basic Overview
Total Sales

```sql

SELECT ROUND(SUM(sales), 2) AS total_sales FROM blinkit;
```
Total Number of Items

```sql

SELECT COUNT(*) AS No_of_items FROM blinkit;
```
Average Sales Per Item

```sql

SELECT ROUND(AVG(sales)) AS Avg_sales FROM blinkit;
```
Average Rating

```sql

SELECT ROUND(AVG(rating)) AS Avg_Rating FROM blinkit;
```
##📦 Sales Breakdown
🔹 By Fat Content
```sql

SELECT item_fat_content, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1 
ORDER BY 2 DESC;
```

🔹 By Item Type
```sql

SELECT item_type, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1 
ORDER BY 2 DESC;
```
🔹 By Outlet Type
```sql

SELECT outlet_type, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1 
ORDER BY 2 DESC;
```
🔹 By Outlet Size
```sql

SELECT outlet_size, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1 
ORDER BY 2 DESC;
```
🔹 By Outlet Establishment Year
```sql

SELECT outlet_establishment_year, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1 
ORDER BY 2 DESC;
```
🔹 By Outlet Location Type
```sql

SELECT outlet_location_type, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1 
ORDER BY 2 DESC;
```
##📚 Cross-Dimensional Insights
🔸 Fat Content by Outlet Location Type
```sql

SELECT outlet_location_type, item_fat_content, ROUND(SUM(sales), 2) AS total_sales 
FROM blinkit 
GROUP BY 1, 2 
ORDER BY 1, 3 DESC;
```
🔸 Combined Metrics by Outlet Type
```sql

SELECT outlet_type, 
       ROUND(SUM(sales), 2) AS total_sales, 
       ROUND(AVG(sales)) AS Avg_sales, 
       COUNT(*) AS No_of_items 
FROM blinkit 
GROUP BY 1;
```
📌 Notes
All queries are executed on the blinkit table.

Aggregates include sales, ratings, and item counts.

Useful for retail sales performance and business strategy analysis.
