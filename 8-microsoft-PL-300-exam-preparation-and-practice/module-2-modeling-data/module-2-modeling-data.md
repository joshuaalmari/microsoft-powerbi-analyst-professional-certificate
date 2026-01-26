# 🚀 Module 2: Modeling Data

This module explores the critical stage of designing a robust data model. It covers the transition from raw data preparation to the creation of efficient schemas, the implementation of complex DAX calculations, and the optimization of model performance for enterprise-level reporting.

---

## 🏗️ 1. Designing a Data Schema

A well-designed schema is the blueprint for accurate analysis, defining how tables relate to ensure consistent results.

### Star Schema vs. Snowflake Schema
* **Star Schema:** The industry standard for Power BI. It consists of a central **Fact Table** (quantitative metrics) surrounded by **Dimension Tables** (descriptive context).
* **Snowflake Schema:** An extension of the star schema where dimension tables are normalized into multiple related tables (e.g., breaking a Product table into Category and Subcategory). This can increase complexity and impact query performance.

### Key Table Types
* **Fact Tables:** Store measurements or metrics of a business process (e.g., sales transactions). They often contain repeated values.
* **Dimension Tables:** Store descriptive attributes about the facts (e.g., products, regions, or salespeople). They are used to group or filter data in the fact table.

---

## 🖇️ 2. Relationships, Keys, and Cardinality

Establishing correct connections between tables is essential for accurate data filtering and reporting.

### Relationship Keys
* **Primary Keys:** Unique identifiers in a dimension table that identify a specific row.
* **Foreign Keys:** Columns in a fact table that establish a link to the primary key of a dimension table.

### Cardinality Types
* **One-to-Many (1:*):** The most common relationship; one record in a dimension table relates to many records in a fact table.
* **One-to-One (1:1):** Both related columns contain unique values.
* **Many-to-Many (*:*):** Both related columns can contain duplicate values. These require careful management to avoid incorrect insights.

### Cross-Filter Direction
* **Single:** Filters flow unidirectionally from the "One" side to the "Many" side.
* **Bi-directional (Both):** Filters flow in both directions. Use sparingly as it can lead to performance issues or ambiguous data paths.
* **CROSSFILTER Function:** A DAX function that temporarily changes the cross-filter direction for a specific measure.

---

## 🧮 3. DAX Calculations and Context

Data Analysis Expressions (DAX) is the formula language used to create new information in your model.

### Calculation Types
* **Calculated Columns:** Computed during data refresh and stored in the model. They consume memory and are ideal for row-level math or for use as slicers.
* **Measures:** Computed on-the-fly during visualization and not stored in the model. They are executed dynamically and integrate any applied filter context.
* **Quick Measures:** Pre-built DAX templates for common calculations like Year-to-Date (YTD) or Year-over-Year (YoY) growth.
* **Calculated Tables:** Tables created via DAX, such as cloned tables (`ALL`), summary tables (`SUMMARIZE`), or combined tables (`UNION`).

### Core DAX Functions
* **CALCULATE:** The only function that can alter the filter context during a calculation.
* **USERELATIONSHIP:** Temporarily activates an inactive relationship (used in role-playing dimensions like Order Date vs. Ship Date).
* **RELATED:** Retrieves a value from another table, provided a relationship exists.

---

## 📊 4. Measure Categorization

Understanding how data aggregates is key to generating accurate insights.

* **Additive Measures:** Can be summed across any dimension (e.g., Total Sales).
* **Semi-Additive Measures:** Can be summed across some dimensions but not all, usually excluding time (e.g., Inventory levels or bank balances).
* **Non-Additive Measures:** Cannot be summed across any dimension; require complex ratios or percentages (e.g., Profit Margin %).

---

## 📂 5. Hierarchies and Path Functions

### Data Hierarchies
* **Structure:** Interconnected fields organized in ranked order (e.g., Year > Quarter > Month).
* **Levels:** Power BI allows a maximum of five levels in a hierarchy.
* **Functionality:** Enables the "Drill Down" feature in visuals to see granular details.

### Path DAX Functions
These functions are essential for analyzing hierarchical data like organizational charts:
* **PATH:** Returns the full path of identifiers as a string.
* **PATHCONTAINS:** Checks if a specific item exists within a path.
* **PATHITEM:** Returns the item at a specific position in the path.
* **PATHITEMREVERSE:** Traces the path backwards.
* **PATHLENGTH:** Measures the depth (number of levels) in a hierarchy.

---

## ⚡ 6. Model Optimization and Monitoring

Maintaining speed and efficiency is a priority as datasets grow.

### Performance Analyzer
A diagnostic tool that records the processing time in milliseconds for:
* **DAX Query:** Time to retrieve data.
* **Visual Display:** Time for the visual to render on the canvas.
* **Other:** Preparation time and background processing.

### Optimization Techniques
* **Data Reduction:** Reducing cardinality and removing unnecessary columns to keep models under capacity limits (e.g., the 1GB limit for shared capacity).
* **Aggregations:** Using summarized tables instead of large raw tables to speed up high-level reporting.
* **Efficient Data Types:** Using numeric types (Integer/Decimal) instead of Text for key columns.

### SQL Source Best Practices
* **Filtering at Source:** Use SQL queries to extract only the necessary data (e.g., the last quarter) rather than loading years of data into Power BI.
* **Aggregation at Source:** Summarize data at the SQL level to reduce the volume of data transferred.
* **Segmenting:** Breaking complex SQL statements into multiple, modular data sources for better maintainability.
