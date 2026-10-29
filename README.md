# FMCG Sales Performance Dashboard - Nigeria | Excel Power Pivot

> **Disclaimer: This is a personal portfolio project. All data is 100% fictitious / simulated for learning purposes and does not represent any real company, brand or sales figures. Product names, stores and regions are inspired by the Nigerian FMCG market structure but all transactions, quantities, revenues and profits are randomly inputed.**

[Excel](https://img.shields.io/badge/Excel-Power%20Pivot-green)
[Data Model](https://img.shields.io/badge/Model-Star%20Schema-blue)
[Dataset](https://img.shields.io/badge/Dataset-Fictitious%20%7C%20Simulated-lightgrey)
[Status](https://img.shields.io/badge/Status-Portfolio%20Ready-brightgreen)

**Live Dashboard - Port Harcourt View (Fictitious Data)**
![Dashboard Port Harcourt](images/01_dashboard_PH_2025_March.PNG)

### Overview
An end-to-end **fictitious** FMCG Sales Analytics solution built entirely in Excel using Data Model, Power Pivot and DAX. Analyzes **simulated** 10,000+ transactions across 5 regions in Nigeria, 5 channels, 20 sales reps, 100 customers, and 70 SKUs.

This project was built to demonstrate how to answer one real business question: **If total revenue drops, is it a Region, Channel, Customer, Rep, or Product problem?**

### The Problem I Solved
Most FMCG sales reports in Excel are flat tables: `Date | Product | Quantity | Revenue`. 
They can show Total Revenue but cannot answer:
- Which Region is driving growth vs dragging?
- Which Customer is responsible for 30% of a region's sales?
- Are we growing vs Same Period Last Year (SPLY)?
- Is Open Market outperforming Modern Trade and Key Account?
- Which Sales Rep is over-dependent and a business risk?
- Which Category/Brand is 70% of the business?

I created this dashboard from a professional Star Schema adding interactive slicers so a Sales Manager can filter by Region/Year/Month and get answers instantly — using fictitious data to replicate a real business scenario.

### The Solution - What I Built
1.  **Cleaned and Modeled Fictitious Data:** Built 7 Dimension tables and 1 Fact table in Excel Power Pivot.
2.  **Created DAX Measures:** Total Quantity, Total Revenue, Total Profit, Profit Margin %, Revenue SPLY, Revenue YoY%, Profit SPLY, Profit YoY%, Contribution %.
3.  **Built Interactive Dashboard:** 8 KPI Cards at top with YoY indicators (green/red arrows), 8 PivotCharts covering every angle, and 3 Slicers.
4.  **Professional Delivery:** Hid all backend sheets (Fact, Dims, Analysis) and left only Dashboard visible - client sees clean view, analyst sees full model.

### Dataset
- **Source: Simulated data created for portfolio only (2023-2025). No real company data used.**
- **Note:** Customer names (e.g. Shoprite Ikeja, Sahad Stores, Kantin Kwari Kano), Products (Power Oil, Mamador, Devon Kings, Maggi, Royco, Peak Milk), and Regions (Lagos, Abuja, Kano, PH, Ibadan) are familiar names used only to make the simulation realistic. All sales values are randomly inputed.
- **FactSales:** SalesID, DateKey, ProductID, CustomerID, EmployeeID, ChannelID, RegionID, Quantity, UnitPrice, TotalRevenue, TotalCost, Profit (~10k simulated rows)
- **DimCalendar:** DateKey, FullDate, Year, MonthNo, MonthName, Quarter
- **DimCustomer:** 100 simulated customers
- **DimEmployee:** 20 simulated reps
- **DimProduct:** 70 simulated products
- **DimBrand:** 10 Brands 
- **DimChannel:** 5 Channels 
- **DimRegion:** 5 Regions

### Data Model - Star Schema
![Data Model Diagram](images/03_datamodel_diagram.PNG)

- FactSales [CustomerID] -> DimCustomer [CustomerID]
- FactSales [EmployeeID] -> DimEmployee [EmployeeID]
- FactSales [RegionID] -> DimRegion [RegionID]
- FactSales [ChannelID] -> DimChannel [ChannelID]
- FactSales [ProductID] -> DimProduct [ProductID]
- FactSales [DateKey] -> DimCalendar [DateKey]
- DimProduct [BrandID] -> DimBrand [BrandID]

All relationships are 1-to-Many, single direction - clean Star Schema.


### Dashboard Walkthrough

**View 1: Port Harcourt Performance (Top Region )**
![Port Harcourt Dashboard](images/01_dashboard_PH_2025_March.PNG)

**View 2: Kano Performance (Same Dashboard, Filtered by Slicer)**
![Kano Dashboard](images/02_dashboard_Kano_2025_March.PNG)

Same dashboard, filtered by RegionName Slicer. No need to build new reports.

Features:
- **Slicers:** RegionName, Year, MonthName - controls all charts
- **KPI Cards:** Qty, Revenue, Profit, Margin, SPLY, YoY% for Revenue & Profit

- **Charts:** Top 5 Customers by Revenue, Monthly Trend (Jan-Apr), Revenue by Channel, Rep Contribution, Regional Contribution, Top 7 Products, Category Contribution, Brand Contribution

### Key Insights - Port Harcourt View (PH | 2025 | March)

**Filter Context:** RegionName = Port Harcourt, Year = 2025, Month = March
**KPIs for this view:** Qty Sold 15,728 | Revenue N26,581,690 | Profit N8,584,675 | Margin 32.3% | Revenue SPLY N20,550,465 | Revenue YoY ▲29% | Profit YoY ▲29% - Strong growth vs last year.

**1. Customer Concentration:**
Top Customer is **PH Wholesale Center (>N3.5M)** in March alone, followed by Oil Mill Market 2 and PH Key Account 2. Top 5 customers are all Port Harcourt based - PH business is heavily driven by wholesale cluster in this month.

**2. Sales Rep Performance:**
**Blessing Wike N9,884,145 (37.18%)** is No.1 rep for PH in March, Joy Peters N7,001,930 (26.34%) second, Emeka Nwosu N4,895,800 (18.42%) third, Chidi Amadi N4,799,815 (18.06%) fourth. Rep concentration risk - top 2 reps = 63.5% of PH March revenue.

**3. Channel Mix for PH:**
**Open Market 33%** is No.1 channel in PH, Modern Trade 22% second, Wholesale 19% third, E-Commerce 13%, Key Account 13%. Traditional trade (Open + Wholesale) = 52% of PH March sales.

**4. Revenue Trend (PH 2025 Jan-Apr):**
Jan ~N21M, Feb drop to ~N13M, Mar peak to ~N26.5M (your selected month), Apr ~N18M. March was the best month - need to check what drove the spike.

**5. Product & Portfolio (PH March):**
**Top 7 Products:** Devon Kings 25L No.1, Mamador 25L No.2, Power Oil 10L No.3.
**Category:** Cooking Oil 73.62% (N19,568,000) dominates PH March, Seasoning 11.56%, Flour 8.73%, Dairy 6.09% - heavy over-concentration on one category.
**Brand:** Devon Kings 28.07% (N7M) No.1 brand, Power Oil 26.06% close second, Golden Penny 6.12%, Dano 3.76%.

**6. Note on Regional Contribution Visual:**
In this screenshot, the Regional Contribution chart still shows all 5 regions (PH N27M 27.24% as top) instead of 100% PH. This visual is not connected to the RegionName slicer in the Data Model - it is showing overall 2025 contribution. To fix: Right-click Regional Contribution PivotChart > Report Connections > tick RegionName slicer. For this view, interpret it as overall context: Port Harcourt remains No.1 region overall.



### Key Insights - Kano View (Kano | 2025 | March) 
**Filter Context:** RegionName = Kano, Year = 2025, Month = March
**KPIs for this view:** Qty 12,109 | Revenue N16,062,245 | Profit N5,202,620 | Margin 32.4% | Revenue SPLY N21,614,465 | Revenue YoY ▼26% (RED) | Profit YoY ▼26% - DECLINING vs last year, opposite of PH.

**1. Performance vs PH:**
PH March was N26.5M (+29% YoY). Kano March is N16M (-26% YoY). Kano sold 12,109 units vs PH 15,728. Kano is underperforming badly in March 2025 and needs attention.

**2. Customer Concentration:**
Top Customer is **Kurmi Market Store (~N2.8M)** - No.1 in Kano, followed by Kano State Market 1, Kano Key Account 2, Kano Wholesale Hub, Sabon Gari Wholesale. All Kano-based wholesale/market customers - similar wholesale dependence as PH but with lower values.

**3. Sales Rep Performance:**
**Kabiru Lawal N5,077,530 (31.61%)** leads Kano, Hauwa Garba N4,367,000 (27.19%) second, Fatima Yusuf N3,572,300 (22.24%) third, Abdul Sani N3,045,415 (18.96%) fourth. More balanced than PH (PH top rep 37%) - better risk distribution in Kano.

**4. Channel Mix - Very Different from PH:**
**Open Market 45% (vs 33% in PH)** - Even more dominant in Kano, Wholesale 30% (vs 19% in PH), Key Account 11%, E-Commerce 9%, Modern Trade only 5% (vs 22% in PH). Kano is almost 75% traditional trade - Modern Trade opportunity is huge but missing.

**5. Revenue Trend (Kano 2025 Jan-Apr):**
Jan ~N30M peak, Feb drop to ~N20M, Mar drop to ~N16M (your selected month - lowest), Apr slight recovery to ~N19M. Continuous decline Jan-Mar - explains the -26% YoY red flag. Needs root cause: stock, pricing, or competition?

**6. Product & Portfolio (Kano March) - Different taste vs PH:**
**Top 7 Products:** Grand Soya 25L No.1 (~N2.5M), Power Oil 25L No.2, Mamador 5L No.3 - Different from PH where Devon Kings 25L was No.1. Kano prefers Grand Soya.
**Category:** Cooking Oil 51.57% (vs 73.62% in PH) - More diversified, Seasoning 28.58% (vs 11.56% in PH) - Kano buys much more seasoning, Flour 11.14%, Dairy 8.72%.
**Brand:** Power Oil 24.49% No.1 in Kano (vs Devon Kings in PH), Mamador 19.80% second, Golden Penny 6.82%.

**7. Note on Regional Contribution Visual:**
Same bug as before - this chart still shows all 5 regions (PH N27M 27.24% top) and is not connected to RegionName slicer. It shows overall 2025 view for context. To fix: PivotChart > Report Connections > tick RegionName. In true Kano-only view, this should show Kano 100%.



| Metric - March 2025 | Port Harcourt | Kano | Insight |
| :--- | :--- | :--- | :--- |
| Revenue | N26,581,690 ▲29% | N16,062,245 ▼26% | PH growing, Kano declining |
| Qty Sold | 15,728 | 12,109 | PH 30% more volume |
| Top Channel | Open Market 33% | Open Market 45% | Kano more traditional |
| Modern Trade | 22% | 5% | Big gap - opportunity in Kano |
| Top Rep | Blessing 37.18% | Kabiru 31.61% | Both high risk but PH worse |
| Top Category | Cooking Oil 73.62% | Cooking Oil 51.57% | Kano more balanced |
| Top Product | Devon Kings 25L | Grand Soya 25L | Regional taste difference |




This drill-down is only possible because of Star Schema + Slicers.

### Skills Demonstrated
**Data Analytics & Business:** FMCG Sales Operations, Trade Marketing Analysis, YoY / SPLY Analysis, Customer Segmentation, Portfolio Analysis

**Technical:** Excel Data Model, Power Pivot, DAX Measures, KPI Design, PivotTable & PivotChart, Slicers & Timelines, Star Schema Modeling, Data Cleaning (Fictitious Data Simulation), Dashboard Storytelling

**Soft:** Problem Solving, Business Insight Translation, Executive Reporting

