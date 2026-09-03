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

The data model connects sales transactions with product, customer, territory, and date dimensions to support interactive analysis across the dashboard.

The model includes:

- Sales order header and detail data for transaction-level analysis.
- Product, subcategory, and category hierarchies for product analysis.
- Customer and territory dimensions for customer and geographical analysis.
- A dedicated date table for time-based analysis.

This structure allows users to analyze sales performance across different business dimensions while maintaining consistent filtering across the dashboard.

## Project Structure

- `Sales Performance Dashboard.pbix` — Power BI dashboard file
- `README.md` — Project documentation
- `Data/` — Source data and dataset references
- `Screenshots/` — Dashboard preview images

## Dashboard Pages

### 1. Executive Overview

Provides a high-level view of overall sales performance, including key sales, order, customer, and quantity metrics. The page also highlights sales trends, product categories, sales channels, and territory performance.

### 2. Product Performance

Focuses on product-level performance by analyzing sales, order quantities, product categories, subcategories, pricing, and territory contribution.

### 3. Customer & Territory

Provides a deeper view of customer and territory performance, including customer distribution, sales person activity, freight, product category performance, and shipping methods.

## Key KPIs

The dashboard tracks the following key performance indicators:

| KPI | Description |
|---|---|
| **Total Sales** | Total sales value generated from the selected orders. |
| **Total Orders** | Number of unique sales orders. |
| **Total Quantity** | Total quantity of products ordered. |
| **Total Customers** | Number of unique customers. |
| **Average Order Value** | Average sales value per order. |
| **Total Tax** | Total tax amount associated with the selected orders. |
| **Online Orders** | Number of orders placed through the online sales channel. |
| **Offline Orders** | Number of orders placed through the offline sales channel. |
