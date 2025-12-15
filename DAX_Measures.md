# DAX Measures Repository

This file contains the core DAX formulas used in the AdventureWorks data model to derive insights for the executive dashboards.

### 1. Key Performance Indicators (KPIs)

**Total Revenue**
Calculates total revenue by iterating through the Sales Data table and multiplying order quantity by the related product price.
```dax
Total Revenue = 
SUMX(
    'Sales Data',
    'Sales Data'[Order Quantity] * RELATED('Product Lookup'[ProductPrice])
)
```
**% of All Orders** 
Calculates the percentage contribution of the current filter context against the total number of orders (All Orders).
```dax
% of All Orders = 
DIVIDE(
    [Total Orders],
    [All Orders]
)
)
```
### 2. Time Intelligence Measures

**Previous Month Orders** 
Calculates the total orders from the previous month to enable period-over-period comparison.
```dax
Previous Month Orders = 
CALCULATE(
    [Total Orders], 
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)
```

**Previous Month Revenue** 
Calculates the total revenue from the previous month to analyze month-over-month growth or decline.
```dax
Previous Month Revenue = 
CALCULATE(
    [Total Revenue],
    DATEADD(
        'Calendar Lookup'[Date], 
        -1, 
        MONTH
    )
)
```

**YTD Revenue (Year-To-Date)** 
Aggregates Total Revenue from the start of the fiscal year up to the current date context.
```dax
YTD Revenue = 
CALCULATE(
    [Total Revenue], 
    DATESYTD('Calendar Lookup'[Date])
)
```

### 3. Moving Averages (Rolling Metrics)

**10-day Rolling Revenue** 
Calculates a moving sum of revenue for the last 10 days to identify short-term trends and smooth out daily volatility.
```dax
10-day Rolling Revenue = 
CALCULATE(
    [Total Revenue],
    DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX('Calendar Lookup'[Date]),
        -10,
        DAY
    )
)
```
**90-day Rolling Profit** 
Calculates the total profit over the last 90 days to visualize quarterly performance trends.
```dax
90-day Rolling Profit = 
CALCULATE(
    [Total Profit],
    DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX('Calendar Lookup'[Date]),
        -90,
        DAY
    )
)
```







