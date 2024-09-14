# Coffee Shop Sales Analysis

## Project Overview
This project provides a comprehensive analysis of coffee shop sales data to identify key trends, performance metrics, and customer purchasing behavior. The analysis includes KPIs, sales trends by time, and breakdowns by product category and store location. Visualizations were created in Power BI, and SQL queries were used to derive detailed insights.

## Data Source
The dataset consists of sales transactions from a coffee shop, detailing transaction dates, times, product categories, unit prices, and quantities sold. The analysis focuses on sales patterns to provide actionable insights for business growth.

## Tools & Technologies
- **Power BI**: Used to create interactive dashboards for visualizing key insights.
- **SQL**: Utilized for data extraction, transformation, and analysis.
- **CSV**: The raw data file format used for analysis.
- **Microsoft Word & PDF**: Documentation of the analysis process and findings.

## Repository Structure
```
Coffee-Shop-Sales-Analysis/ 
├── data/ 
│ └── coffee_shop_sales.csv                      # Raw data file 
├── reports/ 
│ ├── Coffee_Shop_Sales_Report.docx              # Detailed analysis report 
│ └── Coffee_Shop_Sales_Report.pdf               # PDF version of the report 
├── scripts/ 
│ └── Coffee_Shop_Queries.sql                    # SQL scripts for the analysis 
├── images/ 
│ ├── dashboard1.png                             # Screenshot of dashboard 1 
│ └── dashboard2.png                             # Screenshot of dashboard 2 
├── dashboard/ 
│ └── coffee_shop_sales.pbix                     # Power BI dashboard file
└── README.md                                    # Project overview and documentation
```

## Key Insights
1. **Total Sales**:
   - Generated total sales of **$X** in the analyzed period, indicating robust revenue.
2. **Total Orders**:
   - **X orders** were placed, providing insights into customer demand.
3. **Total Quantity Sold**:
   - **X items** sold, showing the popularity of the products offered.
4. **Sales Trends by Day**:
   - Peak sales on **weekends**, aligning with higher foot traffic during these days.
5. **Sales Performance by Category**:
   - **[Top Category]** was the most profitable, driving the highest revenue.
6. **Top Products**:
   - **[Top Product]** was the best-selling item by revenue and quantity.
7. **Sales by Store Location**:
   - **[Top Store]** location outperformed others, suggesting strategic opportunities.
8. **Hourly Sales Trends**:
   - The highest sales occurred during **[Peak Hours]**, indicating busy times for the shop.

## Visualizations
### 1. Overall Sales Performance Dashboard
Provides an overview of key metrics such as total sales, order volume, and sales trends over time. Highlights the busiest days, product categories, and store performance.
![Overall Sales Performance](images/dashboard1.png)

### 2. Top Products and Categories Dashboard
Showcases the top-selling products and categories by revenue and quantity, helping to identify bestsellers and underperformers.
![Top Products and Categories](images/dashboard2.png)

## SQL Analysis
Key SQL queries used in this project include:

### 1. Total Sales
```sql
SELECT ROUND(SUM(unit_price * transaction_qty)) AS Total_Sales
FROM coffee_shop_sales
WHERE MONTH(transaction_date) = 5; -- For the month of May
```
### 2. Sales Trends
```sql
SELECT MONTH(transaction_date) AS Month, ROUND(SUM(unit_price * transaction_qty)) AS Total_Sales
FROM coffee_shop_sales
GROUP BY MONTH(transaction_date)
ORDER BY Total_Sales DESC;
```
### 3. Sales by Product Category
```sql
SELECT product_category, ROUND(SUM(unit_price * transaction_qty), 2) AS Total_Sales
FROM coffee_shop_sales
GROUP BY product_category
ORDER BY Total_Sales DESC;
```
### 4. Top 10 Products by Sales
```sql
SELECT product_type, ROUND(SUM(unit_price * transaction_qty), 1) AS Total_Sales
FROM coffee_shop_sales
GROUP BY product_type
ORDER BY Total_Sales DESC
LIMIT 10;
```
## How to Use This Repository

This repository contains all the necessary files and documentation to explore and replicate the coffee sales analysis. Follow the steps below to make the most out of the project.

### 1. Clone the Repository
Start by cloning the repository to your local machine using the following command:
```bash
git clone https://github.com/yourusername/Coffee-Sales-Analysis.git
```

### 2. Explore the Data
The raw data used for the analysis is located in the `data/` folder. The primary data file is:
- `Coffee_sales.csv`: Contains all sales transactions with details such as order dates, pizza types, quantities sold, and total prices.

### 3. Run the SQL Queries
You can run the SQL queries provided in the `scripts/` folder to extract insights from the data:
- `Coffee_sales_queries.sql`: This file contains all the SQL queries used in the analysis. You can execute these queries in any SQL environment, such as MySQL, PostgreSQL, or SQL Server.

### 4. View the Power BI Dashboard
The interactive dashboard is available in the `dashboard/` folder:
- `Coffee_project.pbix`: Open this file in Power BI Desktop to explore the visualizations and insights interactively.

### 5. Review the Reports
Detailed reports documenting the analysis and findings are located in the `reports/` folder:
- `SQL_queries_REPORT.docx`: A comprehensive report of the analysis, including visualizations and interpretations.
- `SQL_queries.pdf`: A PDF version of the report for easy sharing.

### 6. Modify and Extend the Analysis
Feel free to modify the SQL queries, explore additional data insights, or extend the analysis by adding new visualizations to the Power BI dashboard.

### 7. Contribution
If you would like to contribute to this project, please fork the repository, make your changes, and submit a pull request. Contributions are welcome!

## Conclusion

This analysis provided valuable insights into the sales performance of the Coffee sales, highlighting key trends, top-selling products, and customer preferences. The findings can be used to inform strategic decisions, such as optimizing the menu, improving inventory management, and targeting marketing efforts more effectively. By leveraging the data, the dashboard can enhance its operational efficiency and drive further growth.

The analysis showcased the power of combining SQL with data visualization tools like Power BI to turn raw data into actionable insights.
