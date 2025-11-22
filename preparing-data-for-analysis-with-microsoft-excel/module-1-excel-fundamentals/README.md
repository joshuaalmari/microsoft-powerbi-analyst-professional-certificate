# 📊 Module 1: Excel Fundamentals

This module covers the essential building blocks of Microsoft Excel, establishing the skills necessary to navigate the interface, manage large datasets, and perform foundational data organization tasks like sorting and filtering.

---

## 🖥️ The Excel Interface and File Management

Understanding the layout and file constraints is the first step to efficient data management.

### Key UI Elements
* **Title Bar:** Located at the top, it displays the filename, the Autosave button, and the Search box for finding tools or content.
* **The Ribbon:** Located below the title bar, containing Command tabs (e.g., Home, Insert) which organize hundreds of commands.
    * *Contextual Tabs:* Special tabs (e.g., Chart Design) that only appear when specific items, like a chart, are selected.
* **Formula Bar:** Displays the actual contents of a cell (the formula or data) even if the cell displays a calculated result.
* **Worksheet Grid:** The primary area for data entry, divided into rows and columns where cells intersect.

### File Naming Conventions
* Filenames can contain spaces and capital letters but should avoid special punctuation as some characters are not permitted.
* **Character Limit:** Filenames can have up to 255 characters, though keeping it under 31 is recommended.

---

## 📝 Data Entry and Formatting

Correctly entering and formatting data ensures readability and prevents calculation errors.

### Data Types and Alignment
* **Default Alignment:** Text aligns to the **left**, while numbers align to the **right**.
* **Mixed Data:** Excel treats any entry containing both letters and numbers as **text**.
* **Display Errors:**
    * If a number is too long for the column width, Excel may display it in **Scientific Notation** (e.g., `1E+09`).
    * If the column is too narrow for the content, it may display repeating **Hash Symbols** (`####`).

### Entry Shortcuts
* **Autocomplete:** Excel suggests words based on previous entries in the same column.
* **Autofill:** Using the mouse pointer (which changes to a narrow black cross) on the bottom right corner of a cell to drag and copy data into adjacent cells.
* **Format Painter:** A tool on the Home ribbon that copies format settings from one cell to paint onto others.

### Visualization Tools
* **Wrap Text:** Stacks words vertically within a cell to make the full heading visible without widening the column.
* **Number Formatting:** Tools to set Currency, Percentages (which multiplies the cell content by 100), or Decimal places.

---

## 🌍 Regional Variations and Settings

Excel adapts formats based on geographic location, which is critical for global data compatibility.

* **Date/Time Systems:** Formats vary by region (e.g., `MM/DD/YYYY` vs. `DD/MM/YYYY`) based on Windows settings, though custom formats can be applied via the Number group.
* **Separators:** Regions differ in using commas or periods for decimals.
    * *Impact on Formulas:* If Excel is set to use the comma as a decimal separator, function arguments must be separated by **semicolons**.
* **Date Systems:** Excel defaults to the 1900 date system, but some Mac versions use the 1904 date system, which can affect date calculations.
* **Customization:** These defaults can be overridden in `File > Options > Advanced` by unchecking "Use system separators".

---

## 🗂️ Structuring Workbooks: Rows, Columns, and Sheets

Efficiently managing the structure of a workbook allows for better organization of large datasets.

### Managing Rows and Columns
* **Resizing:** Drag the separator line between headers or **double-click** it to auto-fit the width/height to the content.
* **Hiding/Unhiding:** Used to simplify views without deleting data. To unhide a column, you must first select the columns surrounding the hidden section.
* **Inserting:** New columns appear to the **left** of the selection; new rows appear **above** the selection (or via right-click menu).

### Managing Worksheets (Tabs)
* **Organization:** Tabs can be renamed (double-click) and recolored (right-click) to categorize data.
* **Duplication:** Use the "Move or Copy" command (right-click tab) to create an exact clone of a sheet to preserve original data.
* **Deletion Warning:** Unlike other actions, deleting a worksheet is **permanent** and cannot be reversed using Undo.

---

## 🔍 Navigating Large Data Blocks

Techniques to view and edit massive spreadsheets without losing context.

###
