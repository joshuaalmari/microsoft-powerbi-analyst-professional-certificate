# 🛠️ Module 2: The Right Tools for the Job (Data Acquisition & Transformation)

This module focuses on the critical backend processes of data analysis: identifying the right data, bringing it into the system (Ingestion), managing storage architectures, and cleaning it for analysis (Transformation). It introduces the **ETL** framework and **Microsoft Power Query** as the primary tool for shaping data.

---

## 🎯 Data Identification and Evaluation

Before analysis begins, an analyst must define the business goal to determine what data is required.

### Types of Data
* **Structured Data:** Data organized in a specific format (rows and columns) making it easily searchable.
    * *Examples:* Sales transactions, customer information, inventory levels, financial records.
* **Semi-Structured Data:** Contains tags or markers to separate elements but lacks a rigid schema.
    * *Examples:* Sensor data (logs), JSON files, email metadata.
* **Unstructured Data:** Data that does not fit neatly into rows and columns, making it harder to analyze without advanced processing.
    * *Examples:* Social media posts, customer reviews, images, video, and audio files.

### Evaluation Criteria
When selecting data sources, analysts must ask:
* **Relevance:** Does this data directly answer the business question?
* **Granularity:** Is the data detailed enough (e.g., daily vs. monthly sales)?
* **Connectivity:** Can we connect this external data with internal data to find correlations?

---

## 💾 Data Storage and Management Architectures

Choosing where to store data depends on security, cost, and scalability needs.

| Storage Type | Description | Best Use Case |
| :--- | :--- | :--- |
| **On-Premises** | Data stored on physical hardware within the company's facilities. Offers full control and strict security but has high maintenance costs. | Storing highly sensitive or core operational data (e.g., Financials, HR records) where compliance is critical. |
| **Cloud-Based** | Data stored on remote servers managed by third-party providers (e.g., Azure). Offers high scalability and accessibility via the Internet. | Storing collaborative data (Market Research) or high-volume unstructured data (Social Media) that needs to grow quickly. |
| **Hybrid** | A combination of both. Sensitive data stays on-premises, while less sensitive or high-volume data moves to the cloud. | Organizations undergoing digital transformation or those needing to balance strict security with modern flexibility. |

### Case Study: AdventureWorks Data Strategy
* **Sales & Manufacturing Data:** Structured and sensitive. Requires a solution that allows for scalability due to growth, but also strict access control.
* **Financial Data:** Highly sensitive and structured. Requires the strictest security (likely On-Premises or secured Private Cloud).
* **Social Media & Reviews:** Unstructured and high volume. Requires a Cloud solution to handle the massive scalability needs for storage.

---

## 🔄 The Power BI Workflow

To work effectively, components must be used in the correct sequence.

1.  **Create (Power BI Desktop):** The development phase. Analysts connect to data sources, clean/transform data, build models, and design reports.
2.  **Publish (Power BI Service):** The deployment phase. Reports are uploaded to the cloud to create dashboards and assign security permissions.
3.  **Share (Service & Mobile):** The consumption phase. Stakeholders access dashboards via web browsers or mobile apps to make decisions.

---

## 🏗️ The ETL Process

**ETL** (Extract, Transform, Load) is the industry-standard framework for moving data from source to destination.

### 1. Extract (Gathering & Ingestion)
Retrieving raw data from various sources.
* **Methods:**
    * **Manual Entry:** High risk of error, slow.
    * **File-Based:** Importing Excel/CSV files.
    * **Database Connections:** Direct SQL queries to live systems (efficient).
    * **Web Scraping:** Automated extraction from websites.
    * **Streaming:** Real-time data flow (e.g., IoT sensors).

### 2. Transform (Cleaning & Shaping)
The most time-consuming phase. Raw data is rarely ready for analysis.
* **Tasks:** Removing duplicates, handling missing values (nulls), splitting columns, changing data types (e.g., text to date), and standardizing units of measure.

### 3. Load (Storage)
Writing the cleaned data into the destination (Data Warehouse or Power BI Data Model).
* **Storage Planning:** Organizations must plan for capacity, scalability, and security (encryption, access controls) to ensure data is safe and retrievable.

---

## ⚡ Microsoft Power Query

Power Query is the dedicated **Data Transformation Engine** within Power BI (and Excel). It automates the ETL process.

### Core Features
* **Connectivity:** Connects to hundreds of sources (SQL, Web, Excel, Salesforce).
* **No-Code Transformation:** Provides a graphical interface to clean data without writing code (uses **M Language** in the background).
* **Repeatable Workflows:** Power Query records every step (e.g., "Removed Top 3 Rows", "Changed Type"). When data is refreshed, these steps run automatically, saving hours of manual work.

---

## 🧹 Data Cleaning Strategies

Data cleaning can happen at two stages. Choosing the right location is critical for efficiency.

| Strategy | Description | Pros & Cons |
| :--- | :--- | :--- |
| **Cleaning at Source** | Fixing errors in the original system (e.g., the SQL Database or Excel file). | **Pros:** Fixes it for everyone forever. Best for data integrity.<br>**Cons:** Requires permission/access to the source system. |
| **Cleaning in Power BI** | Using Power Query to filter and fix errors during import. | **Pros:** Does not alter original data; Analyst has full control.<br>**Cons:** Processing repeats every refresh; fixes apply *only* to that report. |

### Common Data Quality Issues
* **Duplicates:** Artificially inflate sales numbers and skew averages.
* **Null Values:** Gaps in data that can break calculations.
* **Inconsistent Formatting:** Mixed date formats (MM/DD vs DD/MM) or mixed casing (e.g., "New York" vs "new york") prevents proper grouping.
