# 📘 Module 2: Using Data Analysis Expressions (DAX) in Power BI

This module delivers a complete foundation in **DAX (Data Analysis Expressions)**—the core calculation language for **Power BI**, **Excel Power Pivot**, and **SQL Server Analysis Services**.

You will learn:

🔹 DAX syntax and data types  
🔹 Operators and functions  
🔹 Row context vs filter context  
🔹 Calculated columns, tables, and measures  
🔹 Time intelligence and table functions  
🔹 Best practices for writing clean, efficient DAX  

---

## 🏗️ 1. DAX Fundamentals

### 📌 1.1 What DAX Is  
DAX is a formula language that provides:

- Functions  
- Operators  
- Constants  
- Expressions  

These allow you to create **custom logic** over your data model—beyond what raw source data provides.

### 🧩 1.2 DAX Formula Structure  
Every DAX expression follows:

```
<Name> = <DAX Expression>
```

Examples:
```
Total Sales = SUM(Sales[Sales Amount])
Ship Date   = 'Date'
Profit      = [Revenue] - [Cost]
```

DAX formulas return either:

- 📊 A **table** → for calculated tables  
- 🔢 A **scalar** → for calculated columns & measures  

---

## 🔠 2. Data Types in DAX

- 📝 Text  
- 🔢 Decimal (Float)  
- 🔢 Whole Number (Integer)  
- 🔁 Boolean  
- 📅 Date/Time  
- 💲 Currency  

DAX performs **implicit conversions** when needed.

---

## 🧮 3. Operators

### ➕ Arithmetic  
`+  -  *  /  ^`

### 🔍 Comparison  
`=  <>  >  >=  <  <=`

### 🔗 Logical  
`&&` (AND), `||` (OR)

### 🧷 Text  
`&` for string concatenation  
Example:  
```
[Region] & ", " & [City]
```

---

## 📚 4. DAX Functions

A function always uses:

```
FUNCTION_NAME(arg1, arg2, ...)
```

Functions span:

- 🧮 Aggregation (SUM, AVERAGE, MIN, MAX…)  
- 🔤 Text (LEFT, CONCATENATE…)  
- 📅 Date/Time (YEAR, MONTH, NOW…)  
- 🔁 Logical (IF, AND, OR…)  
- 🧭 Time Intelligence  
- 🔗 Relational (RELATED, RELATEDTABLE…)  
- 🗃️ Table functions (FILTER, SUMMARIZE, VALUES…)  

---

## 🧱 5. Row Context & Filter Context

### 🟦 Row Context  
Row-by-row evaluation used in:

- Calculated columns  
- Iterators (e.g., SUMX, FILTER)  

Example:
```
Total Sales = Sales[Quantity] * Sales[Unit Price]
```

### 🟧 Filter Context  
Filters applied by:

- Slicers  
- Report/page/visual filters  
- CALCULATE()  

Sample measure:
```
Total Sales = SUM(Sales[Sales Amount])
```

Context changes → result changes dynamically.

### 🔁 Interaction  
Evaluation flow:

1. Filter context selects valid rows  
2. Row context iterates within the filtered subset  

---

## 🧩 6. Calculated Columns

### 💡 What They Are  
Calculated columns:

- Are computed **row by row**  
- Become physical columns stored in the model  
- Work like any regular field  

### ✏️ Example  
```
Total Sales = Sales[Quantity] * Sales[Unit Price]
Profit      = Sales[Total Sales] - Sales[Cost]
Profit %    = DIVIDE(Sales[Profit], Sales[Total Sales])
```

### 🧭 When to Use  
Use a calculated column when:

- You need a **category/label**  
- You need a **sort by column**  
- You need a row-level value independent of filters  

---

## 🗃️ 7. Calculated Tables

### 💡 What They Are  
Tables created using DAX expressions, not imported data.

### 🧪 Clone Table  
```
Cloned Sales = ALL(Sales)
```

### 📊 Summary Table  
```
Annual Sales Summary =
ADDCOLUMNS(
    SUMMARIZE(
        Sales,
        'Date'[Calendar Year],
        Product[Category]
    ),
    "Total Sales", CALCULATE(SUM(Sales[Sales Amount]))
)
```

### 📅 Date Table  
```
Date = CALENDAR(DATE(2015,1,1), DATE(2021,12,31))
```

Or automatically:

```
Date = CALENDARAUTO()
```

---

## 📐 8. Measures (Dynamic Calculations)

### 🌟 Why Measures Are Powerful  
- React to filters dynamically  
- Improve performance  
- Are reusable  
- Are essential for KPIs  

### 🧠 Example  
```
Total Sales = SUM(Sales[Sales Amount])
```
```
Average Order Value =
DIVIDE([Total Sales], DISTINCTCOUNT(Sales[Order ID]))
```

---

## 📊 9. Types of Measures  
### 🟩 Additive  
Can be summed across *all* dimensions  
Examples: Revenue, Quantity Sold  

### 🟧 Semi-Additive  
Summed across some dimensions—but **not time**  
Examples: Inventory, Account Balance  

### 🟥 Non-Additive  
Not meaningful when summed  
Examples: Averages, Ratios  

Correct pattern:
```
AOV = [Total Sales] / DISTINCTCOUNT(Sales[Customer ID])
```

---

## 📈 10. Statistical Functions

### 🔹 Average  
```
AVERAGE(Sales[Quantity])
```

### 🔹 Median  
```
MEDIAN(Support[Response Time])
```

### 🔹 Count  
```
COUNT(Sales[Order ID])
```

### 🔹 Distinct Count  
```
DISTINCTCOUNT(Sales[Customer ID])
```

### 🔹 Min / Max  
```
MIN(Inventory[Quantity])
MAX(Inventory[Quantity])
```

---

## 🧭 11. Time Intelligence

Requires a proper **Date** table.

### 🔁 Functions
- SAMEPERIODLASTYEAR  
- DATESYTD  
- DATESMTD  
- DATESQTD  
- EDATE  

### 🧮 Example  
```
Sales YoY % =
VAR SalesPriorYear =
    CALCULATE(
        [Sales],
        SAMEPERIODLASTYEAR('Date'[Date])
    )
RETURN
DIVIDE(
    [Sales] - SalesPriorYear,
    SalesPriorYear
)
```

---

## 🗂️ 12. Table Functions

### 🧾 DISTINCT  
Unique values:  
```
DISTINCT(Store[Store Name])
```

### 🧾 VALUES  
Returns distinct values including blank:  
```
VALUES(Store[Store Name])
```

### 🧾 UNION  
```
UNION(InventoryUS, InventoryInternational)
```

### 🧾 FILTER  
```
FILTER(Sales, Sales[Quantity] > 10)
```

### 🧾 TOPN  
```
TOPN(10, Customers, Customers[Sales], DESC)
```

---

## 🛠️ 13. Best Practices

### 👍 Use Variables  
```
VAR PriorYearSales =
    CALCULATE([Sales], PARALLELPERIOD('Date'[Date], -12, MONTH))
RETURN
DIVIDE([Sales] - PriorYearSales, PriorYearSales)
```

### 👍 Fully Qualify Columns  
`Sales[Sales Amount]` not `[Sales Amount]`

### 👍 Format DAX with Line Breaks  
More readable, easier to debug.

### 👍 Prefer Measures Over Calculated Columns  
Columns = row-level, static  
Measures = dynamic, context-aware  

---

## 🏁 14. Summary

You now understand:

- The **full DAX language structure**  
- How **context** drives calculation behavior  
- When to use **calculated columns**, **calculated tables**, and **measures**  
- Core statistical, relational, and table functions  
- Best practices for clean, performant DAX  

This module forms the foundation for advanced modeling, optimization, and analytical insight building in Power BI.

