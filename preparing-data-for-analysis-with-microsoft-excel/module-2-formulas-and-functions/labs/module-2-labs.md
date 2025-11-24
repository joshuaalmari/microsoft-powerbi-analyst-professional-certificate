## 📋 Practical Labs & Exercises

The exercises in this module focus on building essential business reporting tools. The projects demonstrate the application of core mathematical functions to construct **financial pricing models** and generate **monthly performance dashboards** for executive review.

---

### 🧪 Lab 1: Calculating Profit and Margin
* **Objective:** Develop a comprehensive financial model for a division's sales data to evaluate pricing strategies. The task involved calculating wholesale costs, shipping fees, retail pricing with complex markups, and final profit margins.
* **Files:**
    * [📂 View Lab Files](./lab-1-calculating-profit-and-margin/)
    * [📊 View Completed Workbook](./lab-1-calculating-profit-and-margin/Revenue%20Figures%20Completed.xlsx)

#### Key Formulas Constructed:
* **Cost Analysis:**
    * **Total Costing:** Calculated the base cost by multiplying volume by wholesale rates, then added shipping fees.
    * **Absolute References (`$`)**: Locked the shipping rate cell reference (e.g., `$P$1`) to ensure the fixed fee was correctly applied to every row when the formula was copied down the dataset.
* **Pricing Strategy (Markup):**
    * **Retail Logic:** Engineered a formula to establish a retail price that covered wholesale costs, individual shipping, and a **50% markup**.
    * **Syntax Control:** Utilized **Parentheses `()`** to strictly control the Order of Precedence, ensuring the markup percentage applied to the *sum* of the costs rather than just one component.
* **Profitability Metrics:**
    * **Margin Calculation:** Derived the profit margin using the standard formula `=(Total Revenue - Total Costs) / Total Revenue` to determine the percentage of actual profit per sale.
* **Efficiency:**
    * Utilized the **Autofill double-click** method to instantly propagate complex formulas across hundreds of rows, ensuring consistent calculation logic throughout the dataset.

---

### 🧪 Lab 2: Preparing a Monthly Sales Report
* **Objective:** Generate a monthly performance report for a high-priority product line ("A2Mountain Bike Frame"). The goal was to aggregate raw daily data into actionable metrics, including total revenue and performance extremes.
* **Files:**
    * [📂 View Lab Files](./lab-2-preparing-a-monthly-sales-report/)
    * [📊 View Completed Workbook](./lab-2-preparing-a-monthly-sales-report/Monthly%20Sales%20Report%20Completed.xlsx)

#### Key Functions Applied:
* **Aggregations (`SUM`):**
    * Calculated **Total Revenue** and **Total Units Sold** to provide headline figures for the monthly review.
    * *Process Note:* Manually adjusted the cell range selection when Excel's AutoSum incorrectly guessed the data block boundaries.
* **Performance Extremes (`MIN` / `MAX`):**
    * Used `MIN` to identify the lowest daily sales volume and `MAX` to identify the peak performance day.
    * Correlated these figures with specific calendar dates to provide context on sales volatility.
* **Operational Metrics (`COUNT` / `AVERAGE`):**
    * **Days in Month:** Used `COUNT` on the Date column to verify the reporting period. *Key Insight:* Leveraged the fact that Excel stores dates as serial numbers to count them mathematically.
    * **Daily Averages:** Used `AVERAGE` to calculate the mean daily revenue, establishing a baseline for future performance comparisons.
* **Formatting:**
    * Verified that Excel automatically applied **Accounting Number Format** to the calculated results to match the source data's currency styling.
