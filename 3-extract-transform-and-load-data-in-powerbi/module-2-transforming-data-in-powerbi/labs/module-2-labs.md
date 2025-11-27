## 📋 Practical Labs & Exercises

This module focuses on the practical application of Power Query to clean, reshape, and combine data. The exercises simulate real-world data preparation tasks required before analysis can begin.

---

### 🧪 Lab 1: Preparing a Dataset
* **Objective:** Clean a raw sales dataset (`SalesFile.xlsx`) containing common data quality issues such as nulls, mixed data types, and duplicates to ensure accurate reporting.
* **Files:**
    * [📂 View Lab Files](./lab-1-preparing-a-dataset/)
    * [📊 View Cleaned Dataset](./lab-1-preparing-a-dataset/Preparing%20a%20Dataset.pbix)

#### Key Actions Performed:
* **Handling Nulls:** Replaced null values in numeric columns (`Units Sold`, `Sales`, `Profit`) with `0` to allow for aggregation, and filled missing dates with a default standard value.
* **Data Type Correction:** Converted `Manufacturing Price` and `Sale Price` to **Decimal Number** format and `Units Sold` to **Whole Number**, fixing errors where text (e.g., "six hundred") prevented calculation.
* **Error Removal:** Used the "Remove Errors" function to automatically drop rows with corrupt data in critical financial columns.
* **De-duplication:** Identified and removed duplicate rows based on the `Products` column to prevent double-counting sales.

---

### 🧪 Lab 2: Apply a Pivot
* **Objective:** Transform a flat list of product details (`Product-Color Model.xlsx`) into a summary table that displays the count of products per color in a matrix format.
* **Files:**
    * [📂 View Lab Files](./lab-2-apply-a-pivot/)
    * [📊 View Pivoted Model](./lab-2-apply-a-pivot/Apply%20a%20Pivot.pbix)

#### Key Actions Performed:
* **Column Management:** Removed unnecessary columns (`Product Name`) to focus the aggregation on Color and Model.
* **Pivoting:** Used the **Pivot Column** feature on the `Color` column, selecting `Model` as the values column.
* **Aggregation:** Applied the **Count (All)** aggregate function to generate a table where unique colors became column headers, showing the total count of models for each color.

---

### 🧪 Lab 3: Appending two tables
* **Objective:** Integrate sales records from a newly acquired subsidiary into the main corporate dataset. The goal was to stack two datasets with different column names into a single, unified "Master Sales" table.
* **Files:**
    * [📂 View Lab Files](./lab-3-appending-data/raw-files)
    * [📊 View Consolidated Model](./lab-3-appending-data/Appending%20Two%20Tables.pbix)

#### Key Actions Performed:
* **Schema Normalization:** Manually renamed columns in the subsidiary's file (e.g., changing `Quantity` to `OrderQty`) to strictly match the headquarters' naming convention, preventing data fragmentation.
* **Appending:** Used **"Append Queries as New"** to create a master table containing all records from both the original `AdventureWorksSales` and the external `OtherSales` files.
* **Validation:** Verified row counts to ensure no records were lost during the consolidation process.

---

### 🧪 Lab 4: Merging two data sources
* **Objective:** Create a comprehensive sales view by joining transactional data with product details. The task involved linking a high-volume Sales table with a separate Product lookup table to bring in descriptive names and pricing.
* **Files:**
    * [📂 View Lab Files](./lab-4-merging-data/raw-files)
    * [📊 View Enriched Model](./labs/lab-4-merging-data/Merging%20Two%20Data%20Sources.pbix)

#### Key Actions Performed:
* **Relationship Mapping:** Identified `ProductKey` as the common unique identifier (Join Key) between the two datasets.
* **Merging:** Performed a **Left Outer Join** to keep all sales transactions while pulling in matching details from the `Product` table.
* **Column Expansion:** Expanded the merged `Product` table column to select specific fields (`Product Name`, `Unit Price`) while removing redundant keys (`ResellerKey`, `EmployeeKey`) to keep the model clean.
