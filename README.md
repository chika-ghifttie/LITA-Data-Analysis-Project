# Sales Analysis

## Project Overview

This project involves the analysis of sales performance for a retail store using Excel, SQL, and Power BI. The goal is to uncover key insights, such as top-selling products, regional performance, and monthly sales trends.

## Data Sources

Sales Data: The primary dataset used for this project is the Capstone Project file. it includes details like OrderID, CustomerID, Product, Region, OrderDate, Quantity, UnitPrice.


## Key Features

- Data Exploration: Initial analysis performed in Excel using pivot tables and formulas to summarize sales data and calculate metrics.
- SQL Queries: Data loaded into SQL Server for advanced querying, extracting insights such as total sales by product category and monthly sales totals.
- Interactive Dashboard: A comprehensive Power BI dashboard visualizing sales performance, including sales overview, top-performing products, regional breakdowns, and user-interactive slicers for data filtering.
## Tools Used:

- Excel - Data exploration and cleaning[Download here](https://microsoft.com)
- SQL Server Management Studio - Data querying and analysis
- Power BI - Creating Reports


## Data Sources

Sales Data: The primary dataset used for this project is the Capstone Project file. it includes details like OrderID, CustomerID, Product, Region, OrderDate, Quantity, UnitPrice.

## Data Cleaning and Preparation

In the initial data preparation phase, we performed the following tasks:
1. Data loading and inspection,
2. Data cleaning and formatting,
3. Data Transformation: Converted data types as needed (e.g., dates, currencies) to facilitate analysis,
4. Filtering: Removed any irrelevant or duplicate entries from the dataset to streamline analysis.

## Exploratory Data Analysis (EDA)

In this phase, I conducted exploratory data analysis to uncover insights and answer key questions regarding sales performance. The following techniques were utilized:
- Pivot Tables: Used pivot tables in Excel to explore and summarize total sales by product, region, and month, facilitating the identification of trends and outliers.
- Visualizations: Created visual representations (e.g., bar charts, line graphs) to visually interpret data and highlight significant findings.

#### Key Questions Addressed:
  -  What are the top-selling products?
  -  How do sales vary by region?
  -  What are the monthly sales trends?
  -  Which days of the week see the highest sales?

 ## Data Analysis
 
The data analysis phase involved using various tools to answer key questions, uncover trends, and provide insights into sales performance. This analysis focused on identifying patterns in the data, with a particular emphasis on product sales, regional performance, and customer behavior.

### Excel Analysis:

- Summarized Sales by Product, Region, and Month: Used pivot tables to view aggregated sales data, making it easy to see which products and regions performed best and identify monthly trends.
- Calculated Key Metrics: Leveraged Excel formulas to calculate average sales per product and total revenue by region, establishing benchmarks for further analysis.
  
### SQL Queries: Extracted Insights
-  Loaded the dataset into SQL Server to run queries that helped answer key business questions.
-   Identified Top Customers: Queried the database to find the top 5 customers based on total purchase amount, providing insights into customer buying patterns.

#### Key queries included:

1.  Retrieving total sales for each product category
  
  ```sql
Select * FROM [dbo].[Sheet1$]
SELECT PRODUCT,
SUM(sales) AS TotalSales
FROM [dbo].[Sheet1$]
GROUP BY product
```
  
2.  Finding the highest-selling product by total sales value

```sql
Select * FROM [dbo].[Sheet1$]
SELECT TOP 1 Product,
MAX(Sales) AS MaxSales
FROM [dbo].[Sheet1$]
GROUP BY Product
ORDER BY MaxSales DESC
SELECT * FROM [dbo].[Sheet1$]
```

3.  Number of Sales Transactions in Each Region

```sql
Select * FROM [dbo].[Sheet1$]
SELECT Region,
COUNT (Sales) AS TotalSalesCount
FROM [dbo].[Sheet1$]
GROUP BY Region
```
  
4.  Calculating the percentage of total sales contributed by each region

  ```sql
  Select * FROM [dbo].[Sheet1$]
  SELECT Region,
SUM(Sales) AS TotalSales
FROM [dbo].[Sheet1$]
GROUP BY Region
ORDER BY TotalSales DESC
```
5. Total Revenue Per Product

```sql
Select * FROM [dbo].[Sheet1$]
SELECT PRODUCT,
SUM(Sales) AS TotalRevenue
FROM [dbo].[Sheet1$]
GROUP BY Product
```

6.  Identify Products With no Sales In The LastQuater

```sql
Select * FROM [dbo].[Sheet1$]
SELECT PRODUCT,
Sales
FROM [dbo].[Sheet1$]
WHERE Sales = 0
```

7.  Top 5 customers based on total purchase amount

  ```sql
Select * FROM [dbo].[Sheet1$]
SELECT TOP 5 customer id,
SUM (Sales) AS TotalPurchaseAmount
FROM [dbo].[Sheet1$]
GROUP BY Customer id
ORDER BY 2 DESC
```
  
### Power BI Dashboard:

- Integrated Analysis into Visualizations: Created an interactive dashboard that presented key metrics, top-selling products, and regional breakdowns, bringing the analysis together in a visual format.
- Monthly and Regional Trends: Used visualizations like line charts and clustered column charts to highlight monthly sales trends and regional performance.
- Enhanced Usability with Slicers: Included slicers for products, year, month, and region to allow stakeholders to interact with the data and filter insights based on specific segments.
  
This analysis provided actionable insights to help the retail store understand its strongest products, best-performing regions, and sales trends over time, ultimately supporting more data-driven business decisions.
    
 






