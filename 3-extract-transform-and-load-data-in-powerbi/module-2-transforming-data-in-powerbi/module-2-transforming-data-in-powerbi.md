# 🛠️ Module 2: Transforming Data in Power BI

This module moves from extraction to **Transformation**, the "T" in ETL. It focuses on using the **Power Query Editor** to clean, shape, and combine data. The goal is to convert raw, messy inputs into a structured, analytical data model using repeatable workflows.

---

## ⚡ Power Query Fundamentals

Power Query is the data transformation engine that sits between the source data and the Power BI model.

### The Interface
* **The Ribbon:** Contains transformation tools organized by tabs (**Home** for common tasks, **Transform** for modifying existing columns, **Add Column** for creating new data).
* **Queries Pane (Left):** Lists all connected tables (queries).
* **Data Preview (Center):** A sample view of the data that updates in real-time as you apply transformations.
* **Applied Steps (Right):** A sequential history of every transformation.
    * **Auditability:** Clicking a previous step shows the data state at that exact moment.
    * **Editability:** Steps can be deleted (**X icon**), reordered, or modified via the **Gear icon**.

### Data Profiling
Before cleaning, analysts must assess data quality.
* **Column Quality:** Visual indicators showing the percentage of Valid, Error, or Empty values.
* **Distribution & Profile:** Histograms enabling quick identification of outliers or anomalies.

---

## 🧹 Data Cleaning & Standardization

Cleaning ensures data accuracy and prevents calculation errors.

### Managing Columns
* **Selection:** Select multiple columns using **Ctrl** (individual) or **Shift** (range).
* **Removal:** "Remove Columns" deletes selected data; "Remove Other Columns" keeps the selection and deletes everything else (safer for future-proofing).
* **Renaming:** Double-click headers to apply business-friendly names.
* **Promoting Headers:** Using "Use First Row as Headers" when importing flat files (CSV/Excel) where the first row contains labels, not data.

### Data Types
Power BI detects types based on the first 1000 rows, but often requires manual correction.
* **Indicators:** The icon to the left of the header indicates the type (e.g., `1.2` for Decimal, `ABC` for Text, `Calendar` for Date).
* **Common Issues:** Numbers stored as Text cannot be aggregated. Dates stored as Text cannot be used for time intelligence.
* **Constraint:** Changing a data type is an applied step; if the source data format changes later, this step may cause a refresh error.

### Handling Errors
* **Null Values:** Gaps in data. Can be fixed by **Filtering** (removing the row) or **Replacing Values** (filling with a default like "0" or "N/A").
* **Duplicates:** Identified by selecting whole rows. The "Remove Duplicates" function keeps the *first* instance and deletes subsequent matches.

---

## 📐 Shaping and Restructuring Data

Structuring data for the data model often requires changing its shape (rows vs. columns).

### Pivot and Unpivot
* **Unpivot (Wide to Tall):**
    * *Scenario:* Data has years as columns (e.g., "Sales 2022", "Sales 2023").
    * *Action:* Transforms these columns into two new columns: **Attribute** (Year) and **Value** (Sales Amount).
    * *Result:* Increases row count, decreases column count. Essential for time-series analysis.
* **Pivot (Tall to Wide):**
    * *Scenario:* Data has a "Metric" column and a "Value" column.
    * *Action:* Turns unique values in the "Metric" column into their own column headers.
    * *Advanced Option:* Requires selecting an **Aggregate Value Function** (e.g., Count, Sum) to handle multiple rows.

---

## 🔗 Combining Data: Append vs. Merge

Techniques for bringing multiple tables together.

### 1. Append Queries (Stacking)
* **Concept:** Adding rows from one table to the bottom of another (Vertical Integration).
* **Best Practice:** Ensure column names and data types match exactly. Mismatched columns will create null values in the output.
* **Modes:**
    * *Append Queries:* Adds data to the current table.
    * *Append Queries as New:* Creates a completely new master table, preserving the originals.

### 2. Merge Queries (Joining)
* **Concept:** Adding columns from one table to another based on a shared identifier (Horizontal Integration).
* **Join Key:** The common column (e.g., `Order ID`) used to match rows.
* **Join Types:**
    * **Left Outer (Standard):** Keep all rows from the primary table, add matches from the secondary table.
    * **Inner Join:** Keep only rows that exist in *both* tables (filters out non-matches).
    * **Full Outer:** Keep all rows from both tables (creates nulls where no match exists).
