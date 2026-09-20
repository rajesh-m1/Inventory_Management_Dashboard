# Inventory Management Dashboard

## Overview
A comprehensive and interactive Excel dashboard built to track stock levels, monitor inventory health, and optimize reordering processes. This project transforms raw transaction and warehouse data into a clear visual interface, enabling quick identification of fast-moving items, stockouts, and capital tied up in inventory.

## 🛠 Tools & Functions used
- **Microsoft Excel:** Dashboard interface and dynamic visualizations.
- **Power Query:** Data extraction, consolidation from multiple sources, and data cleansing.
- **Conditional Formatting:** Changes cell colour according to condition provided.
- **Choosecols function:** Used to extract specific column from a range of data.
- **Filter function:** Used to extract rows of data from a range or table that meet specific criteria.
- **Xlookup function:** Used to search a specific value in the dataset and return a matching result from another row or column.

## ⚙️ Project Workflow (How It Was Built)

### Step 1: Data Extraction and Transformation (ETL)
- Imported the csv file into **Power Query**.
- Promoted the first row to column headers.
- Standardized text casing(**Capitalized Each Product Category Name**).
- Adjusted column data types.
- Refined the table layout by **Renaming**, **Reordering** and **Removing** the unnecessary columns.

### Step 2: Custom Calculations and formulas used
- Created necessary column for KPI calculations.
- Total Inventory Value=[@[Current Stock]]*[@[Unit Cost]]
- 

### Step 4: Dashboard Design and Visualization
- Designed a clean front-end dashboard on a dedicated sheet to summarize the entire inventory ecosystem.
- Utilized bar charts for warehouse stock comparisons and line charts for historical inventory trends.
- Applied **Conditional Formatting** to create visual alerts (e.g., Red for "Stockout/Urgent Reorder", Yellow for "Low Stock", Green for "Healthy").

### Step 5: Interactivity 
- Integrated **Slicers** connected to the data model.
- Enabled users to dynamically filter the dashboard by **Product Category**, **Warehouse Location**, and **Time Period** for granular analysis.

## 📊 Key Metrics Tracked
- Total Inventory Value
- Inventory Turnover Ratio
- Days Sales of Inventory (DSI)
- Stockout Rate
- Active Reorder Alerts

## 🚀 How to Use
1. Clone this repository or download the `.xlsx` file.
2. Open the workbook in Microsoft Excel (2016 or newer recommended).
3. Navigate to the **Dashboard** tab.
4. Use the Product Category and Warehouse slicers to filter the inventory metrics.
