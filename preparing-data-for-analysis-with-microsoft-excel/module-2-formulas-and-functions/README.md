# 🧮 Module 2: Formulas and Functions

This module focuses on the core computational power of Excel. It covers how to construct mathematical formulas, control calculation order with parentheses, use cell referencing (relative vs. absolute), and deploy built-in functions like SUM, AVERAGE, and COUNT.

---

## 📐 The Basics of Formulas

A formula is a calculation performed on values in a range of cells. All formulas in Excel must begin with an **equal sign (`=`)**.

### 1. Operators and Syntax
Formulas use standard mathematical operators to perform calculations:
* **Addition (`+`)**: Adds values (e.g., `=A1+B1`).
* **Subtraction (`-`)**: Subtracts values (e.g., `=A1-B1`).
* **Multiplication (`*`)**: Multiplies values (e.g., `=A1*B1`).
* **Division (`/`)**: Divides values (e.g., `=A1/B1`).

### 2. Static vs. Dynamic Formulas
* **Static:** Contains fixed numbers (e.g., `=10+5`). The result never changes unless you edit the formula.
* **Dynamic:** References cells (e.g., `=A1+B1`). If the data in cell A1 changes, the formula result updates automatically. This allows for "chains of calculations" where one change ripples through the entire workbook.

### 3. External References
Formulas can reference cells in other worksheets or even other workbooks. These are called "links."
* **Syntax:** `SheetName!CellReference` (e.g., `=Products!H2 + A1` adds cell H2 from the "Products" sheet to A1 in the current sheet).

---

## ⚙️ Controlling Calculations (Order of Precedence)

Excel does not always calculate from left to right. It follows the standard mathematical **Order of Precedence** (often remembered by acronyms like BEDMAS/PEMDAS).

### 1. The Hierarchy
Excel processes operators in this specific order:
1.  **Parentheses `()`** (Highest priority)
2.  **Exponents `^`**
3.  **Multiplication `*` and Division `/`** (Equal priority, processed left to right)
4.  **Addition `+` and Subtraction `-`** (Equal priority, processed left to right)

### 2. Using Parentheses
You can override the standard order by using parentheses.
* **Example:** `=2+3*4` equals **14** (multiplication first).
* **Controlled:** `=(2+3)*4` equals **20** (addition inside parentheses first).

### 3. Absolute vs. Relative References
When copying formulas (e.g., using Autofill), it is critical to control how cell references change.
* **Relative Reference (Default):** Adjusts based on the new location. If you copy `=A1+B1` down one row, it becomes `=A2+B2`.
* **Absolute Reference (`$`):** Locks the reference so it does not change.
    * **Syntax:** Add a `$` before the column letter and row number (e.g., `$A$1`).
    * **Shortcut:** Press **F4** while typing the formula to toggle absolute referencing.
    * **Use Case:** Multiplying a column of prices by a single fixed tax rate cell.

---

## 📈 Percentage Calculations

Percentages are mathematical operators in Excel.

### 1. Basic Percentage Formula
* **Logic:** `(Part / Total) * 100`
* **Excel Method:** Divide the part by the total (e.g., `=D2/C2`) and then apply the **% Format** button from the Home ribbon. This automatically multiplies by 100 and adds the symbol.

### 2. Percentage Increase/Decrease
* **Logic:** To increase a number by 10%, multiply it by 110% (or 1.1).
* **Formula:** `=Original_Value * 110%`.

### 3. Percentage Difference (Growth/Decline)
* **Logic:** `(New Value - Old Value) / Old Value`
* **Syntax:** `=(D5-C5)/C5` (Parentheses are required to ensure the subtraction happens before the division).

---

## 🛠️ Introduction to Functions

Functions are predefined formulas that perform complex calculations easily.

### 1. Function Syntax
* **Structure:** `=FUNCTION_NAME(Argument1, Argument2)`
* **Arguments:** The data the function needs to work. Arguments are enclosed in parentheses and separated by commas (or colons for ranges).
    * **Example:** `=SUM(B2:B13)` adds all numbers in the range B2 through B13.

### 2. The "Insert Function" Tool
* **Purpose:** A dialog box that helps you build formulas if you don't know the syntax.
* **Access:** Click the **fx** button next to the formula bar.
* **Features:** Allows searching for functions by category (Math, Financial, etc.) and provides help text for each argument.

---

## ⚡ The AutoSum Shortcut

Located on the **Home** ribbon, AutoSum provides instant access to the five most common functions.

| Function | Description | Note |
| :--- | :--- | :--- |
| **SUM** | Adds all values in a range. | Automatically detects contiguous blocks of numbers. |
| **AVERAGE** | Calculates the arithmetic mean. | Ignores text and empty cells but includes zeros. |
| **COUNT NUMBERS** | Counts cells containing **numeric** values only. | Uses the `COUNT()` function. Does not count text. |
| **MAX** | Returns the largest number in a range. | Useful for identifying peaks (e.g., highest sales month). |
| **MIN** | Returns the smallest number in a range. | Useful for identifying lows. |

* **Watch Out:** AutoSum stops selecting cells when it hits a blank cell or text. Always verify the dotted selection range before pressing Enter.
