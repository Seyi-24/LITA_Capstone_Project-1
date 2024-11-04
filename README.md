# LITA_DATA_ANALYSIS_CLASS_PROJECT


## Table of Content

- Project Overview [Project Overview](#project-overview)
- Data Description [Data Description](#data-description)
- Data Cleaning [Data Cleaning](#data-cleaning)
- Tool Used:
  - Excel Analysis [Excel Analysis](#excel-analysis)
  - MySQL Analysis [MySQL Analysis](#mysql-analysis)
  - Power BI Analysis [Power BI Analysis](#power-bi-analysis)
- Visualization [Visualizations](#visualizations)
- Key Insights and Recommendations [Key Insights and Recommendations](#key-Insights-and-recommendations) 
- Conclusion [Conclution](#conclusion) 

 ### Project Overview 
Sales analysis is crucial for businesses inform data-driven decisions. This project explores sales performance,focusing on top-selling products,regional performance,and monthly sales trends.

 - Objectives:
 1. Identify top-selling products.
 2. Evaluate regional performance.
 3. Analyze monthly sales trend.

 - Methodology
  - Data analysis using Microsoft Excel,MySQL,and Power BI.
  - Data visualizations and insights.

 ### Data Description 
 - Data Source: Public Sales dataset
 - Data Period: January 2023 - August 2024.  

- Variables:
 1. OrderID (Unique identifier for each order 
 2. CustomerId (Unique identifier identifier for each customer)
 3. Product (Product name)
 4. Region. (Geographic region)
 5. OrderDate (Date of order)
 6. Quantity (Number of units sold)
 7. UnitPrice (Price per unit)

- Notes: This dataset represents sales transactions for a retail store.
- Data Format: xlsx

  ### Data Cleaning 
 - Data Import: Imported Sales data into my Microsoft Excel
 - Data Inspection: Reviewed data for duplicates records 
 - Data Transformation: converted data format to YYYY/MM/DD


### Tool Used
- Microsoft Excel for data cleaning and transformation 
- MySQL for analysis 
- Power BI for modeling and visualization

### Excel Analysis 
Objectives: Analyze sales data to identify trends,patterns,and insights.
 
-Steps:
 - Data Preparation: Removed duplicates and created a new column named 'Total Sales'
- Sales Summary:
- Total Sales: 2,101,090 (formula: =SUM(Total Sales Column)
- Average Sales: 211.78 (formula: =AVERAGE(Total Sales Column)
- Top 
- Pivot Tables 
 
 ![Sales Performance Pivot Table](https://github.com/user-attachments/assets/106b61e4-89eb-4ee0-9ad4-5cca1f83ef42)

 This Pivot table sheet shows the summary of total sales by product,region, and month. 


![Excel Sales Performance Chart](https://github.com/user-attachments/assets/0eb6f824-af50-4073-8006-d4e69f1e8996)

- ### MySQL Analysis

1. Total 
Sales by Product Category 

```sql
SELECT SUM(Quantity*UnitPrice) AS TotalSales
FROM lita_capstone_dataset_salesdata
GROUP BY Product
ORDER BY TotalSales DESC;
```

2. Number of Sales Transactions in each Region 

```sql
SELECT Region, COUNT(OrderID) AS Number_of_Sales_Transactions
FROM lita_capstone_dataset_salesdata
GROUP BY Region;
```

3. Highest Selling-Product by Total Sales Value

```sql
SELECT Product,SUM(Quantity*UnitPrice) AS Total_Sales_Value
FROM lita_capstone_dataset_salesdata
GROUP BY Product 
ORDER BY Total_Sales_Value DESC
LIMIT 1;
```

4. Total Revenue by Product 

```sql
SELECT Product, SUM(Quantity*UnitPrice) AS Total_Revenue
FROM lita_capstone_dataset_salesdata
GROUP BY Product
ORDER BY Total_Revenue DESC;
```

5. Monthly Sales Total for the current year 

```sql
SELECT MONTHNAME(OrderDate) AS Month,SUM(Quantity*UnitPrice) AS Total_Sales
FROM lita_capstone_dataset_salesdata
WHERE YEAR(OrderDate) = YEAR(CURRENT_DATE)
GROUP BY MONTHNAME(OrderDate)
ORDER BY Total_Sales DESC;
```

6. Top 5 Customers by Total Purchase Amount

```sql
SELECT CustomerId,SUM(Quantity*UnitPrice) AS Total_Purchase_Amount
FROM lita_capstone_dataset_salesdata
GROUP BY CustomerId 
ORDER BY Total_Purchase_Amount DESC
LIMIT 5;
```

7. Percentage (%) of Total Sales Contributed by each Region 

```sql
SELECT Region,SUM(Quantity*UnitPrice) AS Total_Sales,
(SUM(Quantity*UnitPrice) / (SELECT SUM(Quantity*UnitPrice) FROM lita_capstone_dataset_salesdata * 100 AS percentage 
FROM lita_capstone_dataset_salesdata
GROUP BY Region;
```

8. Products with no Sales in the last Quarter
 
```sql
SELECT p.product
FROM (SELECT DISTINCT product FROM lita_capstone_dataset_salesdata) p
WHERE NOT EXISTS (
SELECT 1
FROM lita_capstone_dataset_salesdata o
WHERE
o.product = p.product AND o.OrderDate >= DATE_SUB)CURDATE(), INTERVAL 3 MONTH)
)
```

- ###Power BI Analysis 

- Shoes lead with the highest sales (613,380), indicating the strong demand of the product.
- Socks has the lowest sales of (180,785), indicating the low demand of the product suggesting opportunities for improvement.

**Total Sales by Region:**

- The South dominates with 44.2% of total sales, making it a crucial market.
- The West lags with 14.3%, indicating potential for growth.

**Total Sales by Month:**

- February 2023 and 2024 has the highest sales, suggesting seasonal demand.
- April records the lowest sales in 2023 and second-lowest in 2024, indicating potential seasonal slump.

**Average Sales per Product:**

- Shirts boast the highest average sales (326.56), indicating strong product appeal.
- Socks have the lowest average sales (121.82), highlighting room for improvement.

**Product Quantity Sold:**

- Hats top the list with 15,929 units sold, demonstrating popularity.
- Jackets has the lowest with 5,452 units sold, suggesting opportunities to boost sales.

### Visualizations 

![Sales Dashboard - Power BI](https://github.com/user-attachments/assets/9eb520c3-55cb-46db-bffd-f94cb518de84)


*Key Insights and Recommendations:*

1. Product Optimization: Focus on improving Socks sales through targeted marketing, product redesign, or pricing adjustments.
2. Regional Growth: Invest in expanding market presence in the West region.
3. Seasonal Strategies: Develop seasonal marketing campaigns to capitalize on February demand and mitigate April slowdowns.
4. Product Development: Consider introducing new Shirt variants or bundling strategies to maintain high sales.
5. Inventory Management: Monitor Hat demand and adjust inventory accordingly to meet customer needs.

### Conclusion:

This analysis provides valuable insights into sales trends, highlighting areas for improvement and opportunities for growth. By addressing these findings, we can refine our business strategies to drive sales, enhance customer satisfaction, and maintain a competitive edge.




