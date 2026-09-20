# Inventory Management Dashboard

## Overview
A comprehensive and interactive Excel dashboard built to track stock levels, monitor inventory health, and optimize reordering processes. This project transforms raw transaction and warehouse data into a clear visual interface, enabling quick identification of fast-moving items, stockouts, and capital tied up in inventory.

## 🛠 Tools & Technologies
- **Microsoft Excel:** Dashboard interface and dynamic visualizations.
- **Power Query:** Data extraction, consolidation from multiple sources, and data cleansing.
- **Power Pivot:** Building a relational data model to connect inventory transactions with product details.
- **DAX (Data Analysis Expressions):** Custom formulas for calculating turnover rates, reorder points, and dynamic inventory status.

## ⚙️ Project Workflow (How It Was Built)

### Step 1: Data Extraction and Transformation (ETL)
- Imported raw inventory logs, purchase orders, and sales data using **Power Query**.
- Consolidated multiple warehouse data files into a single, seamless query.
- Cleaned the data by standardizing SKUs, handling negative inventory anomalies, and formatting transaction dates.

### Step 2: Relational Data Modeling
- Loaded the transformed data into the Excel Data Model via **Power Pivot**.
- Established one-to-many relationships between the primary transaction fact table and dimension tables (e.g., Product Master, Warehouse Locations, Calendar).

### Step 3: Custom DAX Calculations
- Authored custom **DAX** measures to evaluate inventory performance beyond basic sums.
- Created critical measures including:
  - **Current Stock Level** (Net of purchases and sales)
  - **Inventory Turnover Ratio**
  - **Days Sales of Inventory (DSI)**
  - **Dynamic Reorder Point** (Based on average daily sales and lead time)

### Step 4: Dashboard Design and Visualization
- Designed a clean front-end dashboard on a dedicated sheet to summarize the entire inventory ecosystem.
- Utilized bar charts for warehouse stock comparisons and line charts for historical inventory trends.
- Applied **Conditional Formatting** to create visual alerts (e.g., Red for "Stockout/Urgent Reorder", Yellow for "Low Stock", Green for "Healthy").

### Step 5: Interactivity 
- Integrated **Slicers** connected to the data model.
- Enabled users to dynamically filter the dashboard by **Product Category**, **Warehouse Location**, and **Time Period** for granular analysis.

## 🚧 Challenges Faced & Solutions

During the development of this project, I encountered and overcame several technical challenges:

* **Consolidating Fragmented Data Sources:** Inventory data was originally scattered across multiple CSV files for different warehouses, making global reporting tedious.
  * *Solution:* I utilized the **Power Query "Get Data from Folder"** feature to automatically combine and append all warehouse files. Now, when a new month's file is added to the folder, hitting "Refresh" instantly updates the entire dashboard without manual copying and pasting.

* **Calculating Dynamic Reorder Points:** Static reorder points were leading to either overstocking or stockouts due to fluctuating seasonal demand.
  * *Solution:* I implemented custom **DAX measures** to calculate a rolling average of daily sales and multiplied it by the supplier lead time. This created a dynamic reorder point that automatically adjusts to recent sales trends, keeping stock levels optimal.

* **Tracking Real-Time Stock Status:** Standard PivotTables couldn't easily flag items that were dangerously low on stock based on their unique reorder thresholds.
  * *Solution:* I created a DAX measure that evaluated `[Current Stock] < [Reorder Point]` and assigned a status text. I then mapped this to conditional formatting rules on the dashboard to create automated, color-coded visual alerts for the procurement team.

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

## 📸 Dashboard Preview
![Dashboard Screenshot](path/to/your/image.png)
*(Note: Upload a screenshot of your dashboard to the repository and update this image path)*