# 🛠️ Module 2: Transforming Data with Power Query

This module moves from extraction to **Transformation**, the "T" in ETL. It focuses on using the **Power Query Editor** to clean, shape, and combine data. The goal is to convert raw, messy inputs into a structured, analytical data model using repeatable workflows.

---

## ⚡ Power Query Fundamentals

Power Query is the data transformation engine that sits between the source data and the Power BI model.

### The Interface
* **The Ribbon:** Contains transformation tools organized by tabs (**Home** for common tasks, **Transform** for modifying existing columns, **Add Column** for creating new data).
* **Queries Pane (Left):** Lists all connected tables (queries) in the current session.
* **Data Preview (Center):** A sample view of the data that updates in real-time as you apply transformations.
* **Applied Steps (Right):** A sequential history of every transformation.
    * **No "Undo" Button:** Power Query does not have a traditional Ctrl+Z. To undo an action, you must delete the step from this list.
    * **Step Dependency:** Deleting an early step may break subsequent steps that rely on it.
    * **Editability:** You can reorder steps by dragging them or modify settings via the **Gear icon** next to the step name.

---

## 🧹 Data Cleaning & Standardization

Cleaning ensures data accuracy and prevents calculation errors later in the analysis.

### Column Management
* **Removal:** "Remove Columns" deletes selected data; "Remove Other Columns" keeps the selection and deletes everything else. The latter is safer for future-proofing against source schema changes.
* **Renaming:** Renaming columns early ensures consistency, especially before combining tables.
* **Promoting Headers:** Using "Use First Row as Headers" is essential for flat files (CSV/Excel) where the first row contains labels.

### Data Types
Power BI detects types based on the **first 1000 rows**. If the error appears later in the dataset, manual adjustment is required.
* **Decimal Number:** Supports 15-digit precision. Floating point.
* **Fixed Decimal Number:** Fixed to 4 decimal places. Best for **Currency** to avoid rounding errors.
* **Date/Time vs. Date:** Splitting Date/Time into separate columns is often best for model size and filtering.
* **Text:** Any mixed content (numbers + letters) defaults to Text.

### Handling Errors
* **Null Values:** Gaps in data.
    * *Fix:* **Replace Values** (e.g., replacing `null` with `0` or "Unknown") or **Fill Down** (propagating a value to empty cells below it).
* **Duplicates:** Identified by selecting whole rows. "Remove Duplicates" keeps the *first* instance and drops the rest.
* **Row Errors:** The "Remove Errors" function drops rows containing data that violates type rules (e.g., text in a number column), preventing load failures.

---

## 📐 Shaping and Restructuring Data

Structuring data for the data model often requires changing its shape (rows vs. columns).

### Pivot and Unpivot
* **Unpivot (Wide to Tall):**
    * *Scenario:* Data has dates or categories as column headers (e.g., "Jan Sales", "Feb Sales").
    * *Action:* Transforms these multiple columns into two new columns: **Attribute** (the header name) and **Value** (the data).
    * *Result:* Increases row count, decreases column count. Essential for time-series analysis.
* **Pivot (Tall to Wide):**
    * *Scenario:* Data has a "Metric" column (e.g., "Color") and a "Value" column.
    * *Action:* Turns unique values in the "Metric" column into their own column headers.
    * *Requirement:* You must select an **Aggregate Value Function** (e.g., Count, Sum) to determine how to handle intersecting data points.

---

## 🔗 Combining Data: Append vs. Merge

Techniques for bringing multiple tables together.

### 1. Append Queries (Stacking)
* **Concept:** Adding rows from one table to the bottom of another (Vertical Integration).
* **Critical Rule:** Column names and data types must match **exactly**.
    * *Match:* Rows are stacked.
    * *Mismatch:* Power Query creates a new column for the unmatched field and fills it with **Null** values for the other table.
* **Modes:**
    * *Append Queries:* Adds data directly to the current query.
    * *Append Queries as New:* Creates a completely new master table, preserving the original sources.

### 2. Merge Queries (Joining)
* **Concept:** Adding columns from one table to another based on a shared identifier (Horizontal Integration).
* **Join Keys:** The common column used to match rows.
    * *Constraint:* The key column must have the **same data type** in both tables.
    * *Uniqueness:* In a standard lookup scenario, the key in the "lookup" table (e.g., Product List) must be unique.
* **Join Types:**
    * **Left Outer:** Keep all rows from the first table, add matches from the second. (Most Common).
    * **Right Outer:** Keep all rows from the second table, add matches from the first.
    * **Inner Join:** Keep **only** rows that exist in *both* tables.
    * **Full Outer:** Keep all rows from both tables (creates nulls where no match exists).
