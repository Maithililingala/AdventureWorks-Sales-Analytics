# AdventureWorks Sales Intelligence Dashboard
![Power BI](https://img.shields.io/badge/Power_BI-F2C811?style=for-the-badge&logo=powerbi&logoColor=black)
![DAX](https://img.shields.io/badge/DAX-Analysis-00758F?style=for-the-badge&logo=microsoftsqlserver&logoColor=white)
![Snowflake Schema](https://img.shields.io/badge/Data_Modeling-Snowflake-29B5E8?style=for-the-badge&logo=snowflake&logoColor=white)

## 📊 Executive Summary
This project analyzes sales data for AdventureWorks, a global equipment manufacturer. [cite_start]The goal was to resolve data silos and enable executive leadership to track KPIs in real time[cite: 4, 21]. By architecting a Snowflake Schema and developing dynamic DAX measures, this solution reduced decision latency and identified key opportunities in customer segmentation and inventory optimization.

**Key Impact:**
* **Data Architecture:** Integrated 15+ tables into a unified data model.
* **Strategic Insight:** Demographic clustering revealed that **high-income ($100k+) buyers generated 2.3x higher Average Order Value (AOV)**, enabling targeted marketing campaigns to reduce returns.
* [cite_start]**Performance:** Designed 4 executive dashboards to track revenue, profit margins, and return rates[cite: 26].

---

## 🏢 Business Problem
[cite_start]AdventureWorks faced challenges in optimizing operations due to a lack of integration across business units[cite: 21]. The analysis focused on four critical areas:
1.  [cite_start]**Sales Performance:** Evaluating strategies across regions to uncover growth opportunities[cite: 8].
2.  [cite_start]**Customer Retention:** Understanding diverse purchasing patterns to improve Customer Lifetime Value[cite: 11, 12].
3.  [cite_start]**Product Returns:** Identifying root causes of high return rates to protect profit margins[cite: 14].
4.  [cite_start]**Inventory Management:** Forecasting demand to prevent stock shortages or surpluses[cite: 18].

---

## ⚙️ Technical Methodology

### 1. Data Transformation & Modeling
Raw data from the AdventureWorks SQL database was transformed using Power Query. 
* [cite_start]**Preprocessing:** Standardized headers, parsed text delimiters, and added derived columns (e.g., Domain Name, Full Name)[cite: 49, 55].
* [cite_start]**Data Model:** Implemented a **Snowflake Schema**, connecting Fact tables (`Sales`, `Returns`) to Dimension tables (`Territory`, `Customer`, `Product`)[cite: 86]. [cite_start]This structure enabled complex filtering across demographics and product categories[cite: 87].

![Data Model](assets/data-model.png)

### 2. Advanced DAX Calculations
[cite_start]Over 25 DAX measures were developed to support time-series analysis and dynamic aggregation[cite: 91].
* [cite_start]**Time Intelligence:** Created measures like `Previous Month Orders` and `YTD Revenue` using `CALCULATE` and `DATESYTD`[cite: 93, 94].
* [cite_start]**Rolling Metrics:** Implemented `10-day Rolling Revenue` to smooth daily volatility and visualize trends[cite: 95].
* [cite_start]**Scenario Analysis:** Built dynamic parameters to simulate price adjustments and their impact on profit[cite: 307].

*(See `DAX_Measures.md` for the code snippets)*

---

## 📈 Dashboard Showcase

### Executive Overview
[cite_start]**Stakeholders:** CEO, CFO, CMO[cite: 25].
[cite_start]**Insights:** * Weekly revenue peaked in Jan 2022, suggesting strong seasonal/holiday influence[cite: 300].
* [cite_start]Identified a recent dip in monthly revenue coupled with an uptick in return rates[cite: 302].

![Executive Dashboard](assets/exec-dashboard.png)

### Customer Analysis
**Insights:**
* [cite_start]**Segmentation:** High-income professionals drive the majority of revenue[cite: 235].
* [cite_start]**Top Customer:** Mr. Maurice Shan was identified as the highest-value customer, highlighting opportunities for VIP loyalty programs[cite: 236].

![Customer Detail](assets/customer-view.png)

### Product Performance
**Insights:**
* [cite_start]**Quality Control:** "Sport-100 Helmets" showed high return rates, flagging potential quality issues[cite: 301].
* [cite_start]**Category Trends:** Accessories and Bikes dominate order volume[cite: 301].

![Product Detail](assets/product-view.png)

---

## 🚀 Conclusion
[cite_start]The final report delivered a robust analytical platform, not just a static display[cite: 42]. [cite_start]It successfully empowered the sales and marketing teams to tailor strategies based on granular customer behaviors and product performance metrics[cite: 27, 28].
