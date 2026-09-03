# Data Sources

The dashboard was built using the AdventureWorks sample dataset.

The data was retrieved through the LearnSQL API and used to analyze sales orders, products, customers, and territories.

## Source Tables

### Sales

- **Sales Order Header** — Order-level information such as order date, customer, territory, shipping, tax, and sales channel.
- **Sales Order Detail** — Product-level order details including quantity and line total.
- **Customer** — Customer information used for customer-level analysis.

### Product

- **Product** — Product-level information used for product performance analysis.
- **Product Subcategory** — Product subcategory information.
- **Product Category** — Product category information.

### Territory

- **Sales Territory** — Territory information used for regional sales and customer analysis.

## Source Links

- [Sales Order Header](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_SalesOrderHeader?limit=10000&sort=OrderDate&order=ASC)
- [Sales Order Detail](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_SalesOrderDetail?limit=10000&sort=SalesOrderID&order=ASC)
- [Product](https://learnsql.cpetoday.com/api/mssql/adventureworks/Production_Product?limit=10000&sort=ProductID&order=ASC)
- [Product Subcategory](https://learnsql.cpetoday.com/api/mssql/adventureworks/Production_ProductSubcategory?limit=10000&sort=ProductSubcategoryID&order=ASC)
- [Product Category](https://learnsql.cpetoday.com/api/mssql/adventureworks/Production_ProductCategory?limit=10000&sort=ProductCategoryID&order=ASC)
- [Customer](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_Customer?limit=10000&sort=CustomerID&order=ASC)
- [Sales Territory](https://learnsql.cpetoday.com/api/mssql/adventureworks/Sales_SalesTerritory?limit=10000&sort=TerritoryID&order=ASC)

## Data Usage

The dataset was used for analytical and visualization purposes to demonstrate sales performance analysis in Power BI.

The dashboard focuses on sales, orders, quantities, customers, products, sales channels, and territory performance.
