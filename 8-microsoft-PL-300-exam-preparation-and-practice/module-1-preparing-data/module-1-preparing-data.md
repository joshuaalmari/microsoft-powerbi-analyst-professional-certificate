# 🚀 Module 1: Preparing Data

This module provides a deep-dive into the foundational stage of data analysis: identifying, connecting to, and refining data. It covers the technical nuances of data source management, data health evaluation (profiling), and complex transformation logic to ensure datasets are "model-ready."

---

## 🔌 1. Identifying and Connecting to Data Sources

A successful analysis begins with selecting the correct systems to solve a specific business problem.

* **Identifying Data Needs:** Analysts must map business questions to data origins (e.g., social media for marketing trends or support systems for customer satisfaction).
* **Power BI Connectors:** Access to over 100 built-in connectors, including:
    * **File-based:** Excel, CSV, XML, JSON.
    * **Databases:** SQL Server, Azure SQL, MySQL, Oracle.
    * **Online Services:** Google Analytics, Salesforce, Dynamics 365, SharePoint.
* **OneLake Data Hub:** A centralized environment to discover and reuse verified datasets shared within the organization’s tenant.

---

## ⚙️ 2. Data Source Settings & Governance

Managing connections and datasets is critical for maintaining report reliability and security.

### Data Source Management
* **Data Source Settings:** Used to update file paths or server details if a source is moved or renamed.
* **Edit Permissions:** Allows analysts to update credentials (Windows, Database, or Microsoft Account) and authentication methods.
* **Privacy Levels:** Protects data integrity by controlling how data from one source interacts with another:
    * **Private:** Isolated; no sharing with other sources.
    * **Organizational:** Visible only within the organization.
    * **Public:** Accessible by any source.

### Local vs. Shared Datasets
* **Local Datasets:** Offer total control and higher access speed (no internet bottleneck) but are limited in remote accessibility and scalability.
* **Shared Datasets:** Serve as a "Single Source of Truth." They facilitate collaboration, governance (centralized permissions), and cloud-based scalability.

---

## 💾 3. Storage and Connectivity Modes

Power BI Desktop supports three primary connectivity modes to balance performance and real-time needs.

* **Import Mode:** Data is copied into Power BI memory. It offers high-speed performance and full modeling capabilities but requires scheduled refreshes.
* **DirectQuery:** No data is imported; Power BI queries the source in real-time. This is ideal for massive datasets but can slow down visualizations.
* **Dual Mode:** A combination where Power BI chooses between Import and DirectQuery based on the specific query to optimize responsiveness.
* **Live Connection:** Specialized DirectQuery connection for published datasets in the Power BI Service to maintain a single source of truth.

---

## 🛠️ 4. Dataflows and Microsoft Dataverse

### Power BI Dataflows
Dataflows allow for reusable data transformation logic (ETL at scale) stored in the Power BI Service.
* **Entities:** Individual tables within a dataflow.
* **Pipelining:** Dataflows can act as sources for other dataflows (up to a chain depth of 32).
* **Scaling:** Refreshing more than 10 dataflows in a workspace requires a Power BI Premium subscription.

### Microsoft Dataverse
A more advanced cloud-based storage platform suited for datasets updated via Power Apps.
* **Logic and Validation:** Includes Business Rules, Business Process Flows, and Workflows to ensure data quality.
* **Connectivity:** Supports the Tabular Data Stream (TDS) endpoint for direct viewing in Power BI Desktop.

---

## 📊 5. Evaluating Data Quality (Data Profiling)

Analysts must use profiling tools to identify anomalies before moving to analysis. Power BI profiles based on the first 1,000 rows.

* **Column Quality:** Shows the percentage of **Valid**, **Error**, and **Empty** rows.
* **Column Distribution:** Visualizes **Distinct** values (total count including nulls/duplicates) vs. **Unique** values (those appearing exactly once).
* **Column Profile:** Provides statistics such as Min, Max, Average, Standard Deviation, and Null Count.
* **Data View (Table View):** Essential for inspecting data types (Numeric, Date/Time, Text, Boolean) to prevent errors in DAX queries.

---

## 🧹 6. Transforming and Cleaning Data

Refining data involves shaping tables and resolving inconsistencies.

### Common Resolutions
* **Remove Duplicates:** Eliminates redundant rows.
* **Replace Values:** Fixes nulls or misspellings (e.g., replacing "null" with a specific date or a text number with a numeric value).
* **Calculated Columns:** Uses DAX formulas (e.g., `profit = saleprice - cost`) to derive new row-level data.

### Query Management
* **Duplicate Query:** An independent copy; changes in the source do not affect the duplicate.
* **Reference Query:** A dependent link; transformations in the base query flow into the reference query, improving efficiency through pipelining.

### Splitting Techniques
* **By Delimiter:** Splitting by tab, comma, space, or special characters.
* **By Fixed Length/Position:** Useful for structured data like postal codes or mixed Date/Order ID strings.
* **By Transition:** Splitting where text moves from Lowercase to Uppercase, or Digit to Non-Digit.

---

## 🖇️ 7. Combining Data and Relationships

### Merging and Appending
* **Append Queries:** Combines tables by adding rows (top-to-bottom). Requires matching schemas.
* **Merge Queries (Joins):** Combines tables by adding columns (side-by-side) based on a Join Key.
    * **Left/Right Outer:** All from one table, matches from the other.
    * **Inner:** Only matches from both.
    * **Anti-Joins:** Rows that exist in only one of the two tables.

### Table Relationships
* **Keys:** Relationships link a **Primary Key** (unique ID) in a dimension table to a **Foreign Key** in a fact table.
* **Cardinality:**
    * **One-to-Many (1:*):** The standard relationship type.
    * **One-to-One (1:1):** Unique records on both sides.
    * **Many-to-Many (*:*):** Complex relationships requiring careful management.
* **Cross-Filter Direction:** **Single** (One $\rightarrow$ Many) is standard. **Bi-directional** allows filtering in both directions but can cause performance issues and ambiguity.
