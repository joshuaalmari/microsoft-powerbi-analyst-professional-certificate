---

## 📂 Practical Labs & Exercises

This module includes hands-on scenarios using data from **AdventureWorks**, a fictional multinational manufacturing company. Below are the key projects completed to demonstrate proficiency.

### 🧪 Lab 1: Adding data to a worksheet
* **Scenario:** Renee, an executive based in the USA, required a financial report integrating external data from a PDF (`Exchange Rates.pdf`) into an existing Excel workbook (`Sample.xlsx`). The dataset required cleaning, international currency formatting, and structural reorganization for a presentation.
* **Files:**
    * [📂 View Lab Files](./labs/lab-1-adding-data-to-a-worksheet/)
    * [📊 View Completed Workbook](./labs/lab-1-adding-data-to-a-worksheet/Sample_Completed.xlsx)

#### Key Actions Performed:
* **Data Cleaning & Structure:**
    * **Column Management:** Deleted the redundant "State Abbreviation" column to declutter the international dataset.
    * **Data Correction:** Identified and fixed numeric errors where Excel treated numbers as text due to special characters (removed `~` from cell G18).
    * **Data Entry:** Inserted a new "Country" column and utilized **Autofill** to efficiently populate "USA", "Japan", and "Germany".
    * **Segmentation:** Inserted new rows to visually separate data blocks for Japan and Germany.
* **Advanced Formatting:**
    * **Visual Styling:** Standardized headers using **Font Size 14**, background colors, and **Center Alignment**. Used the **Format Painter** to copy these styles to the new Country sub-headers.
    * **Layout:** Applied **Wrap Text** to fix header visibility issues without creating excessive whitespace.
    * **Multi-Currency Formatting:** Applied specific formats to different data ranges:
        * **USA:** Standard Dollar ($).
        * **Germany:** Euro (€).
        * **Japan:** Yen (¥) — *Note: This required accessing the "More Accounting Formats" menu as Yen is not in the default dropdown.*
* **Worksheet Management:**
    * **External Data Integration:** Created a new sheet named "Exchange Rates" and manually entered data derived from an external PDF.
    * **Organization:** Renamed generic tabs to "Sample Figures" and "Exchange Rates" for clarity.
    * **Presentation:** Reordered the tabs for logical flow and **Hid** the irrelevant "Contacts" sheet to focus the stakeholder presentation.

---
