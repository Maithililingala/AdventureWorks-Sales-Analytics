# DAX Code Repository

Below is a collection of the key DAX measures used in the AdventureWorks analysis.

### 1. Time Intelligence
**Previous Month Orders**
Calculates the total orders from the previous month to compare performance.
```dax
Previous Month Orders = 
CALCULATE(
    [Total Orders], 
    DATEADD('Calendar Lookup'[Date], -1, MONTH)
)
