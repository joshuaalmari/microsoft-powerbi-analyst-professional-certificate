# 🎓 Module 4: Course Recap
This final module consolidates the skills acquired throughout the **Extract, Transform, and Load (ETL)** course. It reviews the end-to-end data journey, reinforcing the technical workflows required to build robust, automated, and clean data pipelines in Power BI.

---

## 🔄 Phase 1: Extraction (Data Ingestion)

The foundation of any data project is establishing reliable connections to source data.

### Core Concepts
* **Data Sources:** Connecting to diverse inputs including Local Files (Excel, CSV) and Shared Datasets.
* **Storage Modes:**
    * **Import Mode:** Loads data into memory for speed and full functionality.
    * **DirectQuery:** Connects live to the source for real-time data without caching.
* **Automation:** Using **Triggers** and **Actions** to schedule refreshes, ensuring reports remain up-to-date with frequently changing data without manual intervention.

---

## 🛠️ Phase 2: Transformation (Power Query)

The "Engine Room" of data analysis where raw data is cleaned and shaped.

### Interface & Management
* **Power Query Interface:** Navigating the ribbon, queries pane, and the critical **Applied Steps** list to track transformations.
* **Column Management:** Optimizing models by removing unnecessary columns, ensuring correct **Data Types**, and fixing common errors (nulls, duplicates).

### Advanced Shaping
* **Pivot & Unpivot:** Reshaping tables from "Wide" (summary format) to "Tall" (transactional format) or vice versa to fit analytical needs.
* **Combining Data:**
    * **Append:** Stacking tables vertically (adding rows).
    * **Merge/Join:** Linking tables horizontally (adding columns) based on common keys.

---

## 📤 Phase 3: Loading & Optimization

The final stage ensures data is accurate, efficient, and ready for reporting.

### Data Integrity
* **Staging Areas:** Using intermediate query groups to organize raw data before loading it into the final model.
* **Data Profiling:** Utilizing statistical tools (Column Quality, Distribution, Profile) to detect anomalies and outliers *before* analysis begins.

### Advanced Architecture
* **M Language:** Using the **Advanced Editor** to write or modify the underlying code for complex custom transformations.
* **Efficiency:** Implementing **Dataflows** and **Reference Queries** to create reusable, modular data logic that increases productivity across the organization.


* **Objective:** Demonstrate proficiency by connecting to data, performing advanced cleaning operations, and loading a finalized dataset into Power BI.
