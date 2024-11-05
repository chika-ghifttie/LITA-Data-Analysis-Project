# Sales Analysis

## Table of Content

 - [Project overview](project-overview)
 - [Data Sources](data-sources)
 - [Key Features](key-features)
 - [Tools Used](tools-used)
 - [Data Cleaning and Preparation](data-cleaninig-and-preparation)
 - [Exploratory Data Analysis](exploratory-data-analysis)
 - [Data Analysis](data-analysis)
 - [Results And Findings](results-and-findings)
 - [Recommendations](recommendation)
 - [Limitations](limitation)
 - [Reference](reference)

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

## Results and Findings
The data analysis revealed several significant insights into the retail store’s sales performance, focusing on top-selling products, regional performance, and monthly trends.

1. Top-Selling Products: Identified the top-selling products based on total sales value, with SHOE being the highest earner.

2. Regional Performance: The SOUTHERN REGION is the top-performing region, contributing 44.16% to the total revenue with total sales of 927,820,​ while WEST and NORTH had the lowest.
  Although, the Eastern Region showed consistent growth over time, suggesting potential for targeted marketing efforts.
  
3. Monthly Sales Trends: Sales peaked during FEBRUARY, likely due to seasonal demand or promotional events, while APRIL, SEPTEMBER and DECEMBER experienced the lowest sales.
  
Sales increased during specific periods, suggesting that certain months or seasons drive higher customer engagement.

#### Other Key Findings:

4. Trend by Day of The Week: TUESDAY was identified as the busiest day for sales, highlighting a potential opportunity for targeted promotions or resource allocation on peak days.

5. Percentage of Sales by Region: Each region's contribution to total sales was calculated, showing that SOUTHERN REGION accounted for the largest share.

6. There are no products with no sales in the last quater, indicating that every product has at least some sales.

## Recommendations
  
- Focus on Top-Performing Products:

Since Shoes, Shirt and Hat emerged as top-sellers, consider increasing inventory for them to meet customer demand. Additional promotions for these products could also drive sales further, especially during peak months.

- Expand Efforts in the Southern Region:

Given that the Southern region contributed the highest percentage of total sales (44.16%), it’s recommended to prioritize marketing and promotional activities in this region. This could include targeted ads, region-specific discounts, or expanding product availability in Southern stores.

- Optimize for Peak Sales Months:

The analysis shows seasonal spikes in sales. Planning promotions or stock increases during peak months can capitalize on this demand. Additionally, consider running limited-time offers to boost sales during slower months.

- Leverage Busiest Days of the Week:

Since Tuesday and Thursday were identified as having higher sales, optimize staffing and inventory on these days. Introducing "Midweek Deals" or similar promotions could further increase sales on these high-performing days.

- Address Low/No-Sales Products:

Although there were no products with zero sales, it would be beneficial to monitor low-performing products and assess if any adjustments can be made. Consider bundling these products with high-performing items or adjusting pricing to increase sales.

- Monitor Sales in Low-Performing Regions:

Regions with lower sales can be further investigated to understand potential barriers. Conduct surveys or collect feedback in these regions to understand customer needs, and tailor marketing strategies to address any specific challenges or preferences.

## Limitations

1. Lack of Detailed Product Categorization:

The dataset did not include a "Category" column, limiting the ability to analyze performance by product category. This could have provided insights into demand patterns within specific categories or product types.

2. Absence of Customer Demographic Information:

Without data on customer demographics (such as age, gender, or income level), it was challenging to identify specific customer segments or tailor recommendations to different customer groups.

3. Limited Temporal Scope:

The dataset only covers a specific period (e.g., one year), the findings may not account for longer-term trends, such as year-over-year growth or seasonal variations across multiple years.

4. Absence of Key Data Fields:

Certain critical columns, such as the Sales column, were missing in the initial dataset. This column had to be manually calculated or inputted based on available data, which may introduce some margin of error. The absence of such fields limited the ability to conduct certain types of analysis directly and required additional steps to derive key metrics.

## Reference

i. Dataset Source:

The Sales Dataset was Provided by LITA Africa.

ii. Software and Tools:

- Excel: Used for data cleaning, initial exploration, and creating pivot tables to summarize sales data.
- SQL (SQL Server Management Studio): Utilized for querying and analyzing sales data, identifying trends, and extracting insights.
- Power BI: Employed to design an interactive dashboard that visualizes key insights, including sales trends, regional performance, and top-selling products.

iii. Personal Consultation: 
- Advice and guidance from a peer with experience in data analysis.
- YouTube Tutorials: Various video tutorials on Excel, SQL, and Power BI.






    
 






