# LITA_DATA_ANALYSIS_CLASS_PROJECT


## Table of Content

- Introduction [Introduction](#introduction)
- Project Overview [Project Overview](#project-overview)
- Data Description [Data Description](#data-description)
- Data Cleaning [Data Cleaning](#data-cleaning)
- Tool Used:
  - Excel Analysis [Excel Analysis](excel-analysis)
  - MySQL Analysis 
  - Power BI Analysis

- Insights and Findings 
-Conclusion 

 ### Introduction 
Sales analysis is crucial for businesses inform data-driven decisions. This project explores sales performance,focusing on top-selling products,regional performance,and monthly sales trends.

 ### Project Overview 
 - Objectives:
 1. Identify top-selling products.
 2. Evaluate regional performance.
 3. Analyze monthly sales trend.

 - Methodology:
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
 - Data Transformation: converted data format to YYYY-MM-DD

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

 ![Pivot Table](https://github.com/user-attachments/assets/4be695da-a2b5-4760-be99-0573e420b57d)
 
 This Pivot table sheet shows the summary of total sales by product,region, and month. 

 ![Excel Dashboard](https://github.com/user-attachments/assets/e05cf58d-f029-4354-97fe-fecd2183ee69)


- ### MySQL Analysis

- Total Sales by Product Category 
```sql
SELECT SUM(Quantity*UnitPrice) AS TotalSales
FROM lita_capstone_dataset_salesdata

```

- Number of sales transactions in each region 
```sql
SELECT

```

- Highest selling-product by total sales value
```sql
SELECT 

```

- 


- Shoes lead with the highest sales (613,380), indicating the strong demand of the product.
- Socks has the lowest sales of (180,785), indicating the low demand of the product suggesting opportunities for improvement.

**Total Sales by Region:**

- The South dominates with 42.2% of total sales, making it a crucial market.
- The West lags with 14.3%, indicating potential for growth.

**Total Sales by Month:**

- February 2023 and 2024 show consistently high sales, suggesting seasonal demand.
- April records the lowest sales in 2023 and second-lowest in 2024, indicating potential seasonal slump.

**Average Sales per Product:**

- Shirts boast the highest average sales (326.56), indicating strong product appeal.
- Socks have the lowest average sales (121.82), highlighting room for improvement.

*Product Quantity Sold:*

- Hats top the list with 1,991 units sold, demonstrating popularity.
- Gloves and Socks tie for the lowest with 1,484 units sold, suggesting opportunities to boost sales.

### visualizations 



*Key Insights and Recommendations:*

1. Product Optimization: Focus on improving Socks sales through targeted marketing, product redesign, or pricing adjustments.
2. Regional Growth: Invest in expanding market presence in the West region.
3. Seasonal Strategies: Develop seasonal marketing campaigns to capitalize on February demand and mitigate April slowdowns.
4. Product Development: Consider introducing new Shirt variants or bundling strategies to maintain high sales.
5. Inventory Management: Monitor Hat demand and adjust inventory accordingly to meet customer needs.

### Conclusion:

This analysis provides valuable insights into sales trends, highlighting areas for improvement and opportunities for growth. By addressing these findings, we can refine our business strategies to drive sales, enhance customer satisfaction, and maintain a competitive edge.




