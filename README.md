# 🛒 Power BI E-Commerce Sales Performance Dashboard

## Background & Business Context
This project simulates the analytics function of an **E-Commerce company** seeking real-time visibility into sales and profit performance.  
As part of a complete BI workflow, SQL was used to extract and prepare data from a relational database, while Power BI was leveraged to model, visualize, and deliver **actionable business insights**.

The dashboard serves as an executive analytics hub — helping business leaders monitor **sales growth, profitability trends, customer segments, and regional performance** with interactive and dynamic visuals.

---

## 🎯 Objective
To design and deploy a **fully interactive Power BI dashboard** connected to SQL Server that:
- Tracks **Year-to-Date (YTD)** performance across key business KPIs (Sales, Profit, Quantity, Margin).  
- Enables **drill-down analysis** by product, region, and customer segment.  
- Provides **real-time insights** into business trends through automated DAX measures and dynamic visuals.  
- Demonstrates how Power BI and SQL can be integrated into a seamless **data-to-decision** pipeline.

---

## 💼 Business Value
- **Strategic Visibility:** Empowers executives with a 360° view of YTD and YoY sales performance.  
- **Performance Monitoring:** Highlights top-performing and underperforming products, regions, and categories.  
- **Actionable Insights:** Enables marketing, operations, and sales teams to make faster, data-backed decisions.  
- **Operational Efficiency:** Automates data refresh, reducing manual reporting and improving decision speed.

---

**Model Relationships:**
- `calendar[Date]` → `ecommerce_data[Order Date]` *(One-to-Many)*
- `us_codes[State]` → `ecommerce_data[customer_state]` *(One-to-Many)*

This structured data model ensures consistent and efficient reporting by enabling advanced DAX calculations, filtering across hierarchies, and seamless cross-report interactions.

<img width="655" height="499" alt="image" src="https://github.com/user-attachments/assets/775ace17-de17-481a-b5ef-816fd9ad5911" />

*The design follows a **star schema** layout — optimizing both query performance and analytical flexibility.*

## 📊 Dashboard Features

### Advanced KPI Banner
- Displays **YTD Sales**, **YTD Profit**, **YTD Quantity**, and **Profit Margin**.  
- Each KPI includes **Year-over-Year (YoY) % change** with color-coded conditional formatting:
  - 🟩 **Green** for positive growth  
  - 🟥 **Red** for decline  
- Includes **sparklines** for quick monthly performance visualization.

### Key Visualizations
- **Sales by Category:** Compares current YTD vs. previous YTD with dynamic growth indicators.  
- **Sales by State (Map):** Interactive U.S. map showing regional contribution by sales volume and color-coded by performance.  
- **Top 5 / Bottom 5 Products:** Highlights best and worst performers, allowing quick focus on growth or recovery actions.  
- **Sales by Region:** Donut chart showing regional breakdown (Central, East, South, West).  
- **Sales by Shipping Type:** Distribution of revenue by shipping class for operational optimization.

### Interactivity & Usability
- **Dynamic Filters:** Filter by Customer Segment (Consumer, Corporate, Home Office).  
- **Cross-Filtering:** Click any visual to automatically filter all others.  
- **Year Selectors:** Switch between years for historical comparison.  

---

## ⚙️ Tech Stack & Implementation

| Component | Description |
|------------|--------------|
| **Data Source** | SQL Server relational database; alternative CSV version available. |
| **BI Tool** | Power BI Desktop |
| **Language** | SQL for extraction, DAX for measures & time intelligence |
| **Data Model** | Multi-table schema (Orders, US States, Date) with defined relationships |
| **Time Intelligence** | Custom Date Table using DAX functions like `TOTALYTD()` and `SAMEPERIODLASTYEAR()` |
| **Conditional Formatting** | Dynamic background and icon logic using DAX (`CALCULATE()`, `FILTER()`, `SUMX()`) |
| **Dataset** | Modified Kaggle E-commerce dataset + US State Coordinates |

---

## 📈 Key Analytical Measures (DAX)
- `YTD Sales = TOTALYTD(SUM(Sales[Sales Amount]), 'Date'[Date])`
- `YoY Sales Growth = [YTD Sales] - [PYTD Sales]`
- `Profit Margin = DIVIDE([Total Profit], [Total Sales])`
- `YoY % Change = DIVIDE(([YTD Sales] - [PYTD Sales]), [PYTD Sales])`

---

## 🔍 Business Insights
- **Revenue Growth:** Overall YTD sales show positive YoY growth across most regions, with strongest performance in the **East** and **Central** regions.  
- **Profitability:** Margins remain strong across high-volume categories, though **Furniture** lags behind **Technology** in profit efficiency.  
- **Customer Segments:** The **Consumer** segment drives majority of sales; opportunity exists to expand **Corporate** engagement.  
- **Top Products:** Top 5 SKUs contribute over 25% of total revenue, highlighting potential dependency on a few key products.  
- **Operational Insight:** Shipping Type analysis reveals disproportionate costs in **Second Class**, suggesting a logistics optimization opportunity.

---

###### 👤 About Me
I'm **Micheal Ani**, a **Business Data Analyst & Business Intelligence**. I blend **business acumen** with **data expertise**.
Transforming data into clarity, strategy, and measurable business growth.  
[![LinkedIn](https://img.shields.io/badge/LinkedIn-ANI--MICHEAL-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/micheal-ani-b76716291)
