# AdventureWorks - Data Analysis

An end-to-end analysis of the **AdventureWorks** sales dataset covering customers, products, sales territories and 2017 sales transactions. The goal is to turn raw sales records into clear business insights: what sells, who buys, where, and when.

## Table of Contents

* [Project Overview](#project-overview)
* [Dataset](#dataset)
* [Data Model](#data-model)
* [Tools \& Technologies](#tools--technologies)
* [Methodology](#methodology)
* [Key Metrics](#key-metrics)
* [Analysis \& Insights](#analysis--insights)
* [Key Findings](#key-findings)
* [Repository Structure](#repository-structure)
* [Author](#author)

## Project Overview

AdventureWorks is a fictional bicycle and accessories manufacturer. This project explores its sales data to answer questions such as:

* How did sales, revenue and profit change over 2017 (monthly and quarterly trends)?
* Which products, subcategories and categories drive the most revenue and profit?
* Who are the customers (income, occupation, education, marital status, home ownership) and which segments buy the most?
* Which regions, countries and continents perform best?
* What is the average order value, and how many items does a typical order contain?

## Dataset

The analysis uses six Excel files:

|File|Description|Key field(s)|
|-|-|-|
|`AdventureWorks\_Calendar.xlsx`|Date dimension used for time-based analysis (day, month, quarter, year).|`Date`|
|`AdventureWorks\_Customers.xlsx`|Customer details and demographics.|`CustomerKey`|
|`AdventureWorks\_Product\_Subcategories.xlsx`|Maps each product subcategory to its parent category.|`ProductSubcategoryKey`|
|`AdventureWorks\_Products.xlsx`|Product catalogue with model, color, size, cost and price.|`ProductKey`, `ProductSubcategoryKey`|
|`AdventureWorks\_Sales\_2017.xlsx`|Fact table with 2017 order lines (order date, product, customer, territory, quantity).|`ProductKey`, `CustomerKey`, `TerritoryKey`|
|`AdventureWorks\_Territories.xlsx`|Sales territories by region, country and continent.|`SalesTerritoryKey`|

> Note: column names above follow the standard AdventureWorks sample data. Adjust them if your files differ.

## Data Model

The data follows a star schema: one fact table (Sales) surrounded by dimension tables.

```mermaid
erDiagram
    CALENDAR ||--o{ SALES\_2017 : "OrderDate = Date"
    CUSTOMERS ||--o{ SALES\_2017 : "CustomerKey"
    PRODUCTS ||--o{ SALES\_2017 : "ProductKey"
    TERRITORIES ||--o{ SALES\_2017 : "SalesTerritoryKey = TerritoryKey"
    PRODUCT\_SUBCATEGORIES ||--o{ PRODUCTS : "ProductSubcategoryKey"
```

## Tools \& Technologies

<!-- TODO: keep only the tools you actually used -->

* Microsoft Excel (data cleaning, pivot tables)
* Power BI / Tableau (data modeling and dashboards)
* SQL (querying and aggregation)
* Python (pandas, matplotlib / seaborn)

## Methodology

1. **Data import**: loaded the six Excel files and checked data types and structure.
2. **Data cleaning**: handled missing values, duplicates and inconsistent formats; standardized column names and date fields.
3. **Data modeling**: linked the fact table to the dimension tables using the keys shown above.
4. **Feature engineering**: created calculated fields such as revenue, cost, profit, customer age and income groups.
5. **Analysis \& visualization**: explored trends, rankings and segments, then built charts and dashboards.
6. **Insights**: summarized the findings and business recommendations.

## Key Metrics

|Metric|Definition|
|-|-|
|Total Orders|Distinct count of `OrderNumber`|
|Total Quantity Sold|Sum of `OrderQuantity`|
|Total Revenue|`OrderQuantity` x `ProductPrice`|
|Total Cost|`OrderQuantity` x `ProductCost`|
|Total Profit|Revenue - Cost|
|Profit Margin %|Profit / Revenue|
|Average Order Value|Revenue / Total Orders|

## Analysis \& Insights

### 1\. Sales Trends Over Time

Monthly and quarterly revenue, orders and profit across 2017 using the Calendar table.

<!-- TODO: add chart screenshot and 1-2 sentences on the trend -->

### 2\. Product Performance

Top and bottom products, subcategories and categories by revenue, profit and quantity.

<!-- TODO: add chart screenshot and insight -->

### 3\. Customer Analysis

Customer segments by income, occupation, education, marital status, home ownership and age group.

<!-- TODO: add chart screenshot and insight -->

### 4\. Regional Performance

Sales by region, country and continent using the Territories table.

<!-- TODO: add chart screenshot and insight -->

## Key Findings

<!-- TODO: replace with your actual results -->

* Finding 1: ...
* Finding 2: ...
* Finding 3: ...

**Recommendations**

* ...
* ...

## Repository Structure

```
AdventureWorks-Data-Analysis/
├── data/
│   ├── AdventureWorks\_Calendar.xlsx
│   ├── AdventureWorks\_Customers.xlsx
│   ├── AdventureWorks\_Product\_Subcategories.xlsx
│   ├── AdventureWorks\_Products.xlsx
│   ├── AdventureWorks\_Sales\_2017.xlsx
│   └── AdventureWorks\_Territories.xlsx
├── images           # dashboard and chart screenshots
└── README.md
```

## 

