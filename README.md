# 📊 Sales Performance Dashboard

An interactive **Sales Performance Dashboard** built using **Microsoft Power BI** to analyze sales, revenue, profit, product performance, regional performance, and sales trends.

The dashboard transforms raw SuperStore sales data into meaningful business insights through data cleaning, data modeling, DAX calculations, interactive visualizations, KPIs, and filters.

---

## 📌 Project Overview

The objective of this project is to analyze sales performance and provide a centralized interactive dashboard that helps understand:

- Overall revenue and profitability
- Monthly, quarterly, and yearly sales trends
- Top-selling and low-performing products
- Region-wise sales performance
- Category and sub-category performance
- Customer segment performance
- Payment mode distribution
- Shipping mode performance
- Geographic sales distribution

The dashboard allows users to interact with the data using slicers and explore sales performance dynamically.

---

## 🎯 Project Objectives

The main objectives of this project are:

1. Import and clean the raw sales dataset.
2. Handle missing values and duplicate records.
3. Analyze monthly, quarterly, and yearly sales trends.
4. Identify top-selling products.
5. Identify low-performing products and sub-categories.
6. Compare sales performance across different regions.
7. Compare sales across product categories.
8. Calculate important business KPIs using DAX.
9. Build an interactive dashboard using Power BI.
10. Extract meaningful business insights from the data.

---

## 🗂️ Dataset

### Dataset Name

**SuperStore Sales Dataset**

The dataset contains sales transactions with information about orders, customers, products, locations, sales, quantity, profit, returns, payment modes, and shipping modes.

### Important Columns

| Column | Description |
|---|---|
| Order ID | Unique identifier for an order |
| Order Date | Date on which the order was placed |
| Ship Date | Date on which the order was shipped |
| Ship Mode | Shipping method used |
| Customer ID | Unique customer identifier |
| Customer Name | Name of the customer |
| Segment | Customer segment |
| Country | Country of the customer |
| City | Customer city |
| State | Customer state |
| Region | Sales region |
| Product ID | Unique product identifier |
| Category | Product category |
| Sub-Category | Product sub-category |
| Product Name | Name of the product |
| Sales | Revenue generated from the sale |
| Quantity | Number of units sold |
| Profit | Profit generated |
| Returns | Return information |
| Payment Mode | Payment method used |

---

## 🧹 Data Cleaning & Preparation

The raw dataset was cleaned and transformed using **Power Query** before creating the dashboard.

### Cleaning Steps

- Checked the dataset for missing values.
- Handled missing values appropriately.
- Checked duplicate records.
- Removed unnecessary columns such as `ind1` and `ind2`.
- Converted `Order Date` and `Ship Date` into proper Date format.
- Converted `Sales` and `Profit` into numeric data types.
- Converted `Quantity` into Whole Number format.
- Handled blank values in the `Returns` column without deleting valid sales records.
- Verified the consistency of categorical fields such as Region, Category, and Segment.

---

## 📐 Data Modeling

A separate **Date Table** was created in Power BI to support time-based analysis.

The Date Table was used for:

- Yearly analysis
- Quarterly analysis
- Monthly analysis
- Year-over-year comparison
- Growth rate calculation

A relationship was created between:

`DateTable[Date]`

and

`SuperStore_Sales_Dataset[Order Date]`

This relationship enables accurate time-based analysis and DAX time-intelligence calculations.

---

## 🧮 DAX Measures

The dashboard uses DAX measures to calculate important business metrics.

### Total Revenue

```DAX
Total Revenue =
SUM('SuperStore_Sales_Dataset'[Sales])
