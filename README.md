# TechStore Inc. — SQL Business Analysis

#### SQL Data Analytics Project | E-commerce | Business Problem Approach

## Table of Contents

- [Project Overview](#project-overview)
- [Business Questions](#business-questions)
- [Dataset](#dataset)
- [Analysis Approach](#analysis-approach)
- [Key Findings](#key-findings)
- [Advanced Analysis](#advanced-analysis)
- [Business Recommendations](#business-recommendations)
- [Project Presentation](#project-presentation)

## Project Overview

TechStore Inc. is a growing e-commerce company selling electronics, furniture and accessories across multiple markets.

The objective was to analyse customer, product, sales and sales representative data to identify opportunities to improve sales performance, understand customer behaviour and manage inventory more effectively.

## Business Questions

The analysis focused on four areas:

### Customer Insights

- Who are the highest-value customers?
- Which country generates the most revenue?

### Product & Sales Performance

- Which products are performing best and worst?
- How do sales change over time?

### Sales Representative Performance

- Which sales representatives generate the highest sales?
- How does performance vary across representatives?

### Inventory & Stock

- Which products have high demand but limited available stock?

## Dataset

The analysis used four related datasets:

| Dataset | Purpose |
|---|---|
| Customers | Customer demographics, location and signup information |
| Products | Product, category, brand, price and stock information |
| Orders | Transaction, quantity, date and order status information |
| Sales Reps | Sales representative, region and experience information |

## Analysis Approach

SQL Server was used to analyse the customer, product, order and sales representative data.

**Techniques:** JOINs · Aggregations · Filtering · CTEs · Window Functions

Excel was used to visualise the analysis results.

### Example SQL Query

The following query identifies the top 10 customers by total purchase value.

```sql
SELECT TOP 10
    o.CustomerID,
    c.CustomerName,
    SUM(p.Price * o.Quantity) AS Total_Purchase_Value
FROM Orders AS o
LEFT JOIN Products AS p
    ON o.ProductID = p.ProductID
LEFT JOIN Customers AS c
    ON o.CustomerID = c.CustomerID
GROUP BY
    o.CustomerID,
    c.CustomerName
ORDER BY
    SUM(p.Price * o.Quantity) DESC;
 ```
## Key Findings

- **Customer Value:** The highest-value customer generated approximately **$17.3K** in purchase value.
- **Market Performance:** The **USA generated approximately $27K** in revenue.
- **Product Performance:** **Laptop Pro 14** generated approximately **$37.2K**, while **Wireless Mouse** generated approximately **$2.0K**.
- **Sales Trend:** Sales fell approximately **25%**, from **$28.7K in June to $21.5K in July**.
- **Sales Representative Performance:** A small group of representatives generated substantially higher sales than others.
- **Inventory Risk:** **Standing Desk** demand was **38 units** against **40 units of supply**, leaving **2 units remaining**.

<img width="445" height="272" alt="image" src="https://github.com/user-attachments/assets/f5fe2b91-0cac-4f90-bfe6-b38cff43bd80" />


## Advanced Analysis

An illustrative sales forecast was developed to demonstrate how historical sales data could be used to estimate future performance.

The dataset ends in **July 2024**, so the forecast demonstrates the forecasting method rather than representing a current business prediction.

<img width="412" height="305" alt="image" src="https://github.com/user-attachments/assets/312406cc-6779-4d03-9cfe-85cf4d3aa659" />


## Business Recommendations

1. **Protect high value markets**  
   Maintain performance in the USA while exploring opportunities in other markets.

2. **Prioritise inventory by demand**  
   Restock products where demand is approaching available supply and limit replenishment of lower demand products.

3. **Investigate the July sales decline**  
   Review product category performance and customer feedback to identify potential causes.

4. **Benchmark high performing sales representatives**  
   Analyse their regions, customer mix and sales activity to identify repeatable practices.

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/808de5f4-9ffe-43e8-a92e-245123d24ce1" />


## Project Presentation

[TechStore Inc.pdf](https://github.com/user-attachments/files/32611489/TechStore.Inc.pdf)

