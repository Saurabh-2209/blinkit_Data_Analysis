# blinkit_Data_Analysis

# 🛒 Blinkit Sales Data Analysis (SQL Project)

This project contains SQL queries used to analyze **Blinkit retail sales data**, including total sales, average ratings, item types, outlet types, and more.

---

## 📁 Database Used

```sql
USE blinkit;
```
## 📊 Key Metrics & Insights
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
## 📦 Sales Breakdown
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
## 📚 Cross-Dimensional Insights
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

# 📊 Blinkit Data Analysis (Jupyter Notebook)

This project explores sales, product, and outlet data from Blinkit using Python libraries such as Pandas, Matplotlib, and Seaborn.

---

## 📁 Project Overview
The notebook contains step-by-step data analysis tasks such as:
- Data cleaning  
- Exploratory Data Analysis (EDA)  
- Visualizations  
- Statistical summaries  

---

## 🛠️ Libraries Used
- pandas  
- numpy  
- matplotlib  
- seaborn  

---

# 📈 Visualizations
Multiple plots such as bar charts, box plots, and histograms were used to explore sales distribution, ratings, fat content, and more.

# 📊 Insights
Item fat content affects sales distribution.

Certain item types generate more revenue.

Outlet type and size influence overall sales.

Newer outlets may have different performance trends compared to older ones.

## This analysis helps understand product performance and outlet efficiency in Blinkit. It can assist in inventory planning, outlet expansion, and promotional strategy.

# 📊 BlinkIT Grocery Data Dashboard (Excel)

This repository showcases an interactive **Excel dashboard** created to analyze grocery sales data from **BlinkIT**.

## 🔍 Features

- **Filter Panel** for:
  - Outlet Size (High, Medium, Small)
  - Outlet Location (Tier 1, Tier 2, Tier 3)
  - Item Type (e.g., Dairy, Breads, Frozen Foods)
- Dynamic KPI cards displaying:
  - 💰 Total Sales
  - 🛒 Average Sales
  - 📦 Number of Items
  - ⭐ Average Customer Rating
- Visual elements include:
  - Donut and bar charts
  - Sales trend over the years
  - Comparative analysis of outlet types and sizes

## 📈 Key Insights

- 🥦 **Fruits & Vegetables** are the highest-selling item type ($178.2k)
- 🏬 **Supermarket Type 1** is the top-performing outlet type with $788k in sales and 5,577 items sold
- 📍 **Tier 3 locations** lead in total sales ($472.1k)
- 🔁 Sales peaked in **2018** ($204.52k), indicating a strong performance that year
- **Regular fat content** items dominate with 65% of sales

## 📁 Files

- `BlinkIT Grocery Data Analysis.xlsx` – Source data and Excel dashboard

## 🛠 Tools Used

- **Microsoft Excel**
  - Pivot Tables
  - Slicers for interactivity
  - Charts (Bar, Donut, Line)
  - Conditional Formatting
![Blinkit](https://github.com/user-attachments/assets/4649ea20-5fbb-4972-9d56-4936d60c6da6)
