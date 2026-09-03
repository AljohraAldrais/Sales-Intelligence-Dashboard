# Sales Intelligence Dashboard

An interactive Power BI dashboard designed to provide a clear view of sales performance across products, customers, orders, and territories.

## Project Overview

This project analyzes sales data from the AdventureWorks dataset and presents key business metrics through an interactive three-page Power BI dashboard.

The dashboard is designed to help users explore sales trends, product performance, customer distribution, order activity, and territory-level performance.

## Business Objectives

The dashboard was developed to provide a consolidated view of sales performance and support data-driven analysis.

The main objectives are to:

- Monitor overall sales, orders, quantity, and customer activity.
- Identify sales trends over time.
- Compare product categories and subcategories based on sales and quantity.
- Analyze sales performance across different territories.
- Identify top-performing products and sales representatives.
- Compare online and offline order activity.
- Provide an interactive view of key business metrics through filters and visualizations.

## Dataset & Data Sources

The dashboard uses the AdventureWorks dataset, a sample sales database containing information about orders, products, customers, and sales territories.

Data was retrieved through the LearnSQL AdventureWorks API and imported into Power BI for analysis and visualization.

### Data Tables

The following tables were used in the dashboard:

| Table | Purpose |
|---|---|
| Sales_SalesOrderHeader | Order-level information including dates, customer, territory, tax, freight, and sales channel. |
| Sales_SalesOrderDetail | Order line details including products, quantities, and sales values. |
| Production_Product | Product information used for product-level analysis. |
| Production_ProductSubcategory | Product subcategory information used to analyze product performance. |
| Production_ProductCategory | Product category information used for category-level analysis. |
| Sales_Customer | Customer information used for customer analysis. |
| Sales_SalesTerritory | Territory information used for geographical sales analysis. |

### Data Preparation

The data was imported into Power BI and modeled to support interactive analysis across sales, products, customers, orders, and territories.

## Data Model

The dashboard uses a relational data model that connects sales transactions with product, customer, territory, and date information.

The model consists of two main sales tables supported by several dimension tables:

- **SalesOrders** – Contains order-level information such as order date, customer, territory, tax, freight, and sales channel.
- **SalesOrderDetails** – Contains individual order line information, including products, quantities, and sales amounts.
- **Product** – Provides product-level information and connects products to their subcategories.
- **ProductSubCategory** – Groups products into subcategories and connects them to product categories.
- **ProductCategory** – Provides the highest level of product classification.
- **Customer** – Contains customer information used for customer-level analysis.
- **Territory** – Contains territory information used for geographical analysis.
- **DateTable** – A dedicated date table used for time-based analysis and filtering.

The model allows sales transactions to be analyzed across different dimensions, including time, products, customers, and territories.
