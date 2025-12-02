
# 🎨 Module 2: Navigation and Accessibility

This module focuses on **User Experience (UX)** design in Power BI. It covers the principles of accessible design (ensuring reports work for users with disabilities), the technical implementation of app-like navigation using buttons and bookmarks, and the management of visual interactions to tell a clearer data story.

---

## ♿ Accessibility in Reporting

Accessibility ensures that digital content is usable by everyone, regardless of ability. Power BI supports standards such as **WCAG (Web Content Accessibility Guidelines)** to make reports perceivable, operable, and understandable.

### Core Accessibility Features
* **Screen Reader Compatibility:** Power BI visuals are designed to be read by assistive technology.
* **Alt Text (Alternative Text):** A text description added to visuals that screen readers recite to describe the insight (e.g., "Sales increased by 10% in March").
    * *Configuration:* Format Pane > General > Alt Text.
* **Tab Order:** The sequence in which a keyboard-only user moves through visuals using the **Tab** key.
    * *Default:* Based on the order visuals were created (often chaotic).
    * *Customization:* Must be manually set in the **Selection Pane** to match the logical flow of the report.
* **High Contrast & Focus Mode:** Users can switch to high-contrast themes or expand a single visual to fill the screen for better visibility.
* **"Show Data" Table:** Allows users to view the underlying data of a chart in a screen-reader-friendly tabular format (`Alt + Shift + F11`).

### Visual Design for Accessibility
* **Color Contrast:** Text and background colors must meet a contrast ratio of at least **4.5:1**.
* **Markers:** Adding shapes (squares, triangles) to line chart data points ensures users with color vision deficiencies can distinguish series without relying solely on color.
* **Pattern Fills:** Using textures (stripes, dots) in addition to solid colors for bar and pie charts.

---

## 🖌️ Advanced Formatting & Themes

### Conditional Formatting
A feature that dynamically changes the appearance of visual elements based on data values.
* **Use Cases:**
    * **Data Bars:** Adding horizontal bars inside table cells to visualize magnitude.
    * **Background Color:** Highlighting cells (e.g., Red for negative profit, Green for positive).
    * **Icons:** Adding flags or arrows to indicate status.
* **Logic:** Rules can be defined based on static thresholds or dynamic field values.

### Report Themes
Themes provide a consistent look and feel across a report by defining color palettes, fonts, and visual styles globally.
* **JSON Import:** Custom themes can be imported via JSON files to match corporate branding exactly.
* **Theme Gallery:** A community repository of pre-built themes.
* **Customization:** You can modify the "Current Theme" directly in Power BI Desktop (Name, Text Sizes, Visual Borders) and save it for future use.

---

## 🎛️ Interactive Navigation & Data Exploration

Turning a static report into an interactive application that users can explore.

### Hierarchies & Drill Mode
* **Hierarchy:** Grouping related fields (e.g., Year > Quarter > Month > Day) to create a path for exploration.
* **Drill Down:** Allows users to move from a high-level view to a granular view within the *same* visual.
    * *UI Controls:* Drill Down (Pitchfork icon), Go to Next Level (Double Arrow), Expand All (Split Arrow).

### Drill-Through
A navigation method that takes the user from a summary page to a separate, detailed report page filtered to a specific data point.
* **Setup:** Add a data field to the **Drill-through** well on the destination page. Power BI automatically adds a "Back" button.
* **Action:** Right-click a data point on the source page > Drill Through > [Page Name].

### Cross-Filtering vs. Cross-Highlighting
Controls how selecting data in one chart affects other charts on the page.
* **Cross-Highlighting (Default):** Dims the unselected data in related charts but keeps the full context visible. Good for seeing "Part-to-Whole".
* **Cross-Filtering:** Completely removes unselected data from related charts. Good for focusing analysis.
* **Configuration:** Managed via **Format > Edit Interactions**.

---

## 🔘 Buttons, Bookmarks, and Actions

These features allow developers to build custom navigation logic and "App-like" behavior.

### Buttons
Clickable elements that trigger specific **Actions**:
* **Page Navigation:** Jumps to a specific report page.
* **Back:** Returns to the previous view.
* **Bookmark:** Activates a saved report state.
* **Q&A:** Opens the natural language query explorer.
* **Web URL:** Opens an external website.
* **Clear All Slicers:** Resets all filters on the page.

### Bookmarks
Bookmarks capture the **exact state** of a report page at a specific moment.
* **Captured States:**
    * **Data:** Current filters and slicers.
    * **Display:** Which visuals are visible/hidden (via Selection Pane).
    * **Current Page:** Which page is active.
* **Use Cases:** Creating toggle switches (e.g., hiding a chart and showing a table), resetting a report to default, or telling a data story by stepping through specific views.

### Hyperlinks (URLs)
* **In Tables:** Columns categorized as **Web URL** will render as clickable links in Table/Matrix visuals.
* **In Text Boxes:** Text can be highlighted and linked to external resources.

---

## 📑 Layout Management (The Selection Pane)

The **Selection Pane** is the "Layer Manager" for Power BI, critical for complex designs.
* **Z-Order:** Dragging items up/down the list changes which visual sits "on top" of another.
* **Visibility:** Toggling the **Eye Icon** hides/shows visuals. This is the core mechanism behind interactive Bookmark toggles.
* **Grouping:** Combining multiple visuals into a **Group** allows them to be moved, resized, or hidden as a single unit, simplifying report maintenance.
