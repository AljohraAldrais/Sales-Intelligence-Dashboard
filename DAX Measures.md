# DAX Measures

The following DAX measures were created to support the dashboard analysis and KPI calculations.

## Sales & Order Measures

### Total Sales

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

