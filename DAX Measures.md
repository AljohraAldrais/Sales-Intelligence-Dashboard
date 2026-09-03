# DAX Measures

The following DAX measures were created to support the dashboard analysis and KPI calculations.

## Sales & Order Measures

### Total Sales

```DAX
Total Sales =
SUM(SalesOrderDetails[LineTotal])
```

### Total Orders

```DAX
Total Orders =
DISTINCTCOUNT(SalesOrders[Order ID])
```

### Total Quantity

```DAX
Total Quantity =
SUM(SalesOrderDetails[OrderQty])
```

### Average Order Value

```DAX
Average Order Value =
DIVIDE([Total Sales], [Total Orders])
```

### Total Tax

```DAX
Total Tax =
SUM(SalesOrders[Tax Amount])
```

### Total Customers

```DAX
Total Customers =
DISTINCTCOUNT(Customer[CustomerID])
```

### Online Orders

```DAX
Online Orders =
CALCULATE(
    [Total Orders],
    SalesOrders[Online Order] = 1
)
```

### Offline Orders

```DAX
Offline Orders =
CALCULATE(
    [Total Orders],
    SalesOrders[Online Order] = 0
)
```

## Date Table

### DateTable

```DAX
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
```
