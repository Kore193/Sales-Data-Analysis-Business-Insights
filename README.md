# Sales Data Analysis & Business Insights
### End-to-End Global Superstore Analysis using Python, SQL, Excel, and Power BI

This project analyzes Global Superstore sales data across regions, products, customers, segments, shipping modes, and time periods. It combines Python EDA, SQL business analysis, an Excel dashboard, and an interactive Power BI report.

## Project Overview
- **Python:** data preparation and Exploratory Data Analysis (EDA)
- **SQL:** SQL-based business analysis
- **Microsoft Excel:** analysis, PivotTables, KPI summaries, and dashboard creation
- **Power BI:** data modeling, DAX measures, interactive reporting, and cross-page filtering
- **Git & GitHub:** version control and project sharing

## Business Problem
Raw retail data does not immediately show which regions, products, customers, and segments contribute most to sales or how performance changes over time. This project investigates those patterns and presents them in a format that supports business review and further analysis.

## Project Objectives
- Clean and prepare the sales dataset.
- Explore data quality, distributions, and sales patterns using Python.
- Answer business-oriented questions with SQL.
- Analyze performance and build a dashboard in Excel.
- Build a multi-page interactive Power BI report.
- Compare sales across regions, categories, sub-categories, customer segments, and shipping modes.
- Validate key metrics and communicate findings supported by the data.

## Dataset
The cleaned dataset used for the Power BI report contains **9,788 rows and 19 columns**, covering **2015–2018**. Fields include Order ID, Order Date, Ship Date, Ship Mode, Customer ID, Customer Name, Segment, Country, City, State, Postal Code, Region, Product ID, Category, Sub-Category, Product Name, Sales, Year, and Month.

The dataset does **not** contain Profit, Quantity, Discount, or Shipping Cost, so this project does not claim to analyze those measures.

## Tools & Technologies
| Tool | Purpose |
|---|---|
| Python | Data preparation and EDA |
| Pandas, NumPy | Data manipulation and numerical analysis |
| Matplotlib, Seaborn | Data visualization |
| Jupyter Notebook | Python analysis |
| MySQL | SQL-based business analysis |
| Microsoft Excel | Analysis, PivotTables, KPI summaries, and dashboard |
| Power BI Desktop | Data model and interactive dashboards |
| Power Query | Data preparation within Power BI |
| DAX | Measures and date-related calculations |
| Git & GitHub | Version control and project sharing |

---

## 1. Python Exploratory Data Analysis
Python was used to understand the dataset and prepare it for further analysis.

### Data Preparation & Quality Checks
The workflow included checking the dataset structure and data types, inspecting missing values, handling missing Postal Code values, removing duplicate records, converting Order Date and Ship Date to datetime, checking date consistency, and validating the prepared dataset.

### EDA Areas
- Region-wise and state-wise sales
- Category-wise and sub-category-wise sales
- Customer segment sales
- Monthly sales trends
- Segment × Category analysis
- Region × Category analysis
- Shipping mode analysis
- Overall business performance

## 2. SQL Business Analysis
MySQL was used to answer business-oriented questions about sales and customers.

### Analysis Areas
- Overall sales and order analysis
- Region-wise sales performance
- Category and sub-category analysis
- Customer sales analysis
- Monthly sales analysis
- Sales contribution by category
- Ranking sub-categories within categories
- Top customers within each region
- Customers performing above their regional average

### SQL Concepts Used
`SELECT`, `WHERE`, `DISTINCT`, `GROUP BY`, `HAVING`, `ORDER BY`, aggregate functions, `CASE WHEN`, subqueries, CTEs, JOINs, window functions, `RANK()`, and `LAG()`.

## 3. Excel Analysis & Dashboard
Microsoft Excel was used for business analysis and a management-style dashboard.

### Analysis Areas
- Data validation checks
- Regional sales analysis
- Category × Segment analysis
- Monthly sales trend
- Segment, category, and sub-category performance
- Region × Category analysis
- Shipping mode analysis
- Region × Segment analysis

### Excel Features
- Excel Tables
- `SUMIFS`, `COUNTA`, and `UNIQUE`
- PivotTables and PivotCharts
- Distinct Count
- KPI summaries
- Dashboard layout and design

### Excel Dashboard KPIs
- Total Sales
- Total Orders
- Total Customers
- Average Order Value

The Excel dashboard summarizes performance through KPIs and visuals such as sales by region, product category, month, and customer segment.

## 4. Power BI Data Modeling & Dashboard

Power BI was used to build a three-page interactive report for exploring sales performance at executive, product, customer, and regional levels.

### Data Model & Preparation
- Loaded the cleaned Global Superstore CSV.
- Created a dedicated `Date_Table` using the order-date range.
- Added Year, Month Number, Month, Year Month, and Year Month Sort fields.
- Sorted Month by Month Number and Year Month by Year Month Sort for chronological visuals.
- Created a one-to-many relationship from `Date_Table[Date]` to `Global_Superstore_Cleaned[Order Date]`.
- Created DAX measures for key sales and customer metrics.
- Synchronized Year, Region, Category, and Segment slicers across report pages.

### DAX Measures
```DAX
Total Sales =
SUM(Global_Superstore_Cleaned[Sales])

Total Orders =
DISTINCTCOUNT(Global_Superstore_Cleaned[Order ID])

Total Customers =
DISTINCTCOUNT(Global_Superstore_Cleaned[Customer ID])

Average Order Value =
DIVIDE([Total Sales], [Total Orders])

Sales per Customer =
DIVIDE([Total Sales], [Total Customers])
```

### Page 1 — Executive Overview
- Total Sales, Total Orders, Total Customers, and Average Order Value
- Monthly Sales Trend
- Sales by Region
- Sales by Category
- Year, Region, Category, and Segment slicers

### Page 2 — Sales & Product Analysis
- Sales by Sub-Category
- Top 10 Products by Sales
- Sales by Category
- Sales by Ship Mode
- Sales by Segment
- Sales by Year
- Product detail table

### Page 3 — Customer & Regional Analysis
- Sales by Country
- Top 10 Customers by Sales
- Sales by Segment
- Sales by Region
- Top 10 States by Sales
- Shipping-mode analysis
- Customer detail table

### Interactivity & Validation
- Synchronized slicers filter report pages by Year, Region, Category, and Segment.
- Baseline KPIs were checked with slicers cleared.
- Date sorting was configured to support chronological analysis.

### Baseline Power BI Metrics
With all slicers cleared, the validated baseline values for the current cleaned dataset are:

| KPI | Value |
|---|---:|
| Total Sales | 2,246,545 |
| Total Orders | 4,916 |
| Total Customers | 793 |
| Average Order Value | Approximately 456.99 |

Recheck these values if the source data or model changes.

---

## Key Business Insights
The following findings were reported from the project analysis.

### Regional Performance
- West generated the highest total sales.
- East was the second-highest sales-generating region.
- South generated the lowest sales among the four regions.
- In the Excel regional analysis, West contributed 31.53% of sales and South contributed 17.28%.

### Product Performance
- Technology generated the highest sales among the three main categories.
- Furniture and Office Supplies also contributed to total sales.
- Phones was the highest-selling sub-category by sales.

### Customer Segment
- Consumer generated the highest sales among the three customer segments.
- Corporate and Home Office contributed the remaining sales.

### Shipping
- Standard Class was the most frequently used shipping mode.
- Standard Class also generated the highest total sales among the shipping modes.

### Regional Category Performance
- Technology was the highest-sales category in East, South, and West.
- Furniture generated the highest category sales in Central.

## Business Recommendations
1. Monitor high-performing regions while investigating opportunities in lower-performing regions.
2. Examine Technology's contribution to sales and compare performance across its sub-categories.
3. Investigate sales drivers for high-performing sub-categories such as Phones.
4. Compare lower-performing categories and regions over time before deciding on improvement actions.
5. Monitor Standard Class usage and compare it with other shipping modes.
6. Use monthly sales trends to identify periods of higher and lower demand.

These are exploratory recommendations based on sales patterns. The dataset does not include profit, cost, or discount fields to assess margins or campaign effectiveness.

## Project Structure
```text
global-superstore-sales-analysis/
├── README.md
├── data/
│   └── global_superstore_cleaned.csv
├── python/
│   └── Global_Superstore_EDA.ipynb
├── sql/
│   └── Retail_Sales_SQL.sql
├── excel/
│   └── Global_Superstore_Analysis.xlsx
├── powerbi/
│   └── Global_Superstore_Sales_Analysis.pbix
└── screenshots/
    ├── python_eda.png
    ├── sql_analysis.png
    ├── excel_dashboard.png
    ├── powerbi_executive_overview.png
    ├── powerbi_sales_product_analysis.png
    └── powerbi_customer_regional_analysis.png
```

Update filenames to match the files you actually commit. Include the dataset only if you have permission to redistribute it; otherwise, provide source instructions or a small sample.

## How to Explore the Project
1. Review the Python notebook for data preparation and EDA.
2. Open the SQL script in MySQL to inspect the business-analysis queries.
3. Open the Excel workbook to explore the analysis and dashboard.
4. Open the Power BI `.pbix` file in Power BI Desktop.
5. Use the synchronized Year, Region, Category, and Segment slicers to explore different views.
6. Clear slicers to return to baseline metrics.

## Project Outcome
Completed an end-to-end retail sales analytics project spanning Python EDA, SQL business analysis, an Excel dashboard, and a three-page interactive Power BI report. The work combines data exploration, query-based analysis, KPI development, data modeling, visualization, and baseline validation.

## Limitations
The current dataset does not contain Profit, Quantity, Discount, or Shipping Cost. As a result, this project does not measure profitability, units sold, discount impact, or shipping cost.

---
**Project:** Sales Data Analysis & Business Insights  
**Dataset:** Global Superstore  
**Tools:** Python | SQL | Excel | Power BI  
**Focus:** Data Analytics | EDA | SQL | Dashboarding | Business Insights
