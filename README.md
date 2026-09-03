# Sales Intelligence Dashboard

An interactive Power BI dashboard designed to provide a clear and comprehensive view of sales performance across products, customers, orders, sales channels, and territories.

The project uses the AdventureWorks sample dataset and presents the data through an interactive three-page dashboard designed for business analysis and performance monitoring.

---

## Project Overview

The Sales Intelligence Dashboard provides an interactive view of sales performance across multiple business dimensions.

The dashboard allows users to analyze:

- Overall sales and order performance
- Sales trends over time
- Product and category performance
- Customer distribution
- Territory-level performance
- Sales representative activity
- Online and offline order activity
- Product quantity and sales contribution
- Freight and shipping performance

The dashboard is designed to make key business information easier to understand through KPIs, charts, comparisons, and interactive filters.

---

## Business Objectives

The main objective of this project is to provide a centralized view of sales performance and support data-driven decision-making.

The dashboard was developed to:

- Monitor total sales, orders, quantity, and customer activity.
- Analyze sales trends over time.
- Compare product categories and subcategories based on sales and quantity.
- Evaluate sales performance across different territories.
- Identify top-performing products.
- Analyze sales activity by sales representative.
- Compare online and offline order activity.
- Analyze customer distribution across territories.
- Evaluate freight and shipping performance.
- Provide an interactive analytical experience through filters and visualizations.

---

## Dataset

The project uses the **AdventureWorks** sample sales dataset.

AdventureWorks is a sample relational database containing sales, product, customer, order, and territory information.

The dataset was retrieved through the LearnSQL AdventureWorks API and imported into Power BI for data preparation, modeling, analysis, and visualization.

---

## Data Sources

The following AdventureWorks tables were used as sources for the Power BI data model:

| Table | Purpose |
|---|---|
| `Sales_SalesOrderHeader` | Order-level information including order dates, customers, territories, tax, freight, and sales channel. |
| `Sales_SalesOrderDetail` | Order line information including products, quantities, and line totals. |
| `Production_Product` | Product information used for product-level analysis. |
| `Production_ProductSubcategory` | Product subcategory information used to analyze product performance. |
| `Production_ProductCategory` | Product category information used for category-level analysis. |
| `Sales_Customer` | Customer information used for customer analysis. |
| `Sales_SalesTerritory` | Territory information used for regional and geographical analysis. |

### Source References

The data was retrieved from the LearnSQL AdventureWorks API using the following endpoints:

| Table | Source |
|---|---|
| `Sales_SalesOrderHeader` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_SalesOrderHeader?limit=10000&sort=OrderDate&order=ASC) |
| `Sales_SalesOrderDetail` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_SalesOrderDetail?limit=10000&sort=SalesOrderID&order=ASC) |
| `Production_Product` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Production_Product?limit=10000&sort=ProductID&order=ASC) |
| `Production_ProductSubcategory` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Production_ProductSubcategory?limit=10000&sort=ProductSubcategoryID&order=ASC) |
| `Production_ProductCategory` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Production_ProductCategory?limit=10000&sort=ProductCategoryID&order=ASC) |
| `Sales_Customer` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_Customer?limit=10000&sort=CustomerID&order=ASC) |
| `Sales_SalesTerritory` | [LearnSQL API](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_SalesTerritory?limit=10000&sort=TerritoryID&order=ASC) |

---

## Data Preparation

The source data was imported into Power BI using Power Query.

The data preparation process included:

- Connecting Power BI to the AdventureWorks API.
- Loading the required sales, product, customer, and territory tables.
- Reviewing and preparing the source data for analysis.
- Establishing relationships between the relevant tables.
- Creating a dedicated date table for time-based analysis.
- Preparing the data model to support interactive filtering and cross-analysis.
- Creating DAX measures for the dashboard KPIs and analytical calculations.

---

## Data Model

The Power BI data model connects sales transactions with the relevant product, customer, territory, and date information.

The model includes:

- Sales order header data for order-level analysis.
- Sales order detail data for product, quantity, and sales analysis.
- Product, subcategory, and category information for product analysis.
- Customer information for customer-level analysis.
- Territory information for geographical analysis.
- A dedicated date table for time-based analysis.

This structure allows users to analyze sales performance from different business perspectives while maintaining consistent filtering across the dashboard.

---

## DAX Measures

The dashboard uses DAX measures to calculate the main KPIs and analytical metrics.

```DAX
Total Sales =
SUM(SalesOrderDetails[LineTotal])

Total Orders =
DISTINCTCOUNT(SalesOrders[Order ID])

Total Quantity =
SUM(SalesOrderDetails[OrderQty])

Average Order Value =
DIVIDE([Total Sales], [Total Orders])

Total Tax =
SUM(SalesOrders[Tax Amount])

Total Customers =
DISTINCTCOUNT(Customer[CustomerID])

Online Orders =
CALCULATE(
    [Total Orders],
    SalesOrders[Online Order] = 1
)

Offline Orders =
CALCULATE(
    [Total Orders],
    SalesOrders[Online Order] = 0
)

DateTable =
ADDCOLUMNS(
    CALENDAR(
        MIN(SalesOrders[Order Date]),
        MAX(SalesOrders[Order Date])
    ),
    "Year", YEAR([Date]),
    "Month Number", MONTH([Date]),
    "Month", FORMAT([Date], "MMM"),
    "Quarter", "Q" & FORMAT([Date], "Q"),
    "Year Month", FORMAT([Date], "YYYY-MM")
)
