# 📊 Sales & Profitability Analysis Dashboard

An end-to-end interactive Power BI dashboard designed to evaluate financial performance, sales distributions, cost structures, and profitability margins across dynamic state territories and product categories.

---

## 📸 Dashboard Screenshots

### 1. Sales Overview
![Sales Overview](screenshots/Sales.png)

### 2. Profitability Analysis
![Profit Analysis](screenshots/Profit.png)

### 3. Detailed Financial Performance
![Details](screenshots/Details.png)

---

## 📌 Executive Summary & Business Insights
This project translates raw transactional sales data into strategic financial indicators. By calculating net costs (COGS), tax-excluded revenues, and customer segmentation thresholds, the dashboard highlights top-performing sales territories (e.g., California) and isolates low-margin products.

---

## 🧠 Advanced DAX & Financial Modeling Highlights
Below are key DAX calculations and data transformation techniques implemented in this project:

* **Net Cost Calculation (COGS):** Calculated item-level cost by subtracting net profit from tax-excluded revenue:
  `Cost = [Total Excluding Tax] - [Profit]`
* **Delivery Duration Optimization (`AVERAGEX`):** Cleaned date anomalies by verifying valid date keys before computing average delivery times:
  `Avg Delivery Duration = AVERAGEX(FactSale, IF(FactSale[Delivery Date Key] > 0, FactSale[Delivery Date Key] - FactSale[Invoice Date Key]))`
* **Territory Specific Aggregations:** Utilized `CALCULATE` to dynamically isolate regional performance (e.g., California & Nevada Sales).
* **Customer & Product Segmentation (`VAR` & `SUMX`):** Implemented high-value customer identification (>300K) using optimized `SUMX` and `FILTER` logic for enhanced performance over heavy grouping functions.
* **Data Integration (`LOOKUPVALUE`):** Merged dimension attributes (`StockItemName`) into transactional tables via foreign keys (`StockItemKey`) with fallback handling for missing records.
* **Dynamic Performance Classification (`SWITCH` / Nested `IF`):** Categorized sales performance into visual KPIs (`Amazing`, `Excellent`, `Average`, `Poor`) based on multi-tiered revenue brackets (<2M, <5M, <8M).

---

## 🔑 Core Features
* **Financial Metrics:** Tracks `Total Sales`, `COGS`, `Total Tax`, `Profitability %`, and `Delivery Durations`.
* **Multi-Page Experience:** Clean navigation across Sales, Profit, and Details tabs with synchronized slicers.
* **Conditional Formatting:** Color-coded performance matrix tables for immediate regional analysis.

---

## 🛠️ Tools & Technologies
* **Power BI Desktop**
* **DAX (Data Analysis Expressions)** — Advanced Measures, Calculated Columns, Variables (`VAR`), and `CALCULATE` Filters.
* **Power Query** — Data Cleansing & Transformation.
* **Data Modeling** — Star Schema Architecture.

---

## 📂 Repository Contents
* `Sales_And_Profitability_Analysis.pbix` — Interactive Power BI Dashboard file.
* `Sales_And_Profitability_Analysis.pdf` — Exported multi-page report.
* `screenshots/` — High-resolution images of report pages.

---

## 👤 Author
* **Ziad Abdelaziz**
