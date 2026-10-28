# Customer Behavior & Retail Shopping Trends Analysis

This repository contains a complete, industry-standard, end-to-end data analytics workflow designed to simulate the real responsibilities of an enterprise data analyst. The project covers the full data lifecycle: data exploration and engineering in Python, relational modeling in PostgreSQL, and custom dashboard development in Tableau.

---

## 📌 Project Overview

The goal of this project is to translate raw consumer transaction data into strategic business intelligence to optimize retail marketing strategies and product positioning.

- **Data Engineering & Preparation (Python):** Cleaned, standardized, and transformed raw transaction logs using Pandas, handling missing distributions and engineering custom customer features.
- **Relational Database Analytics (SQL):** Loaded the engineered data schemas into a PostgreSQL instance to run advanced queries on demographic revenue splits and customer retention.
- **Business Intelligence & Reporting (Tableau):** Designed and deployed a custom, fully interactive data visualization dashboard to track core customer metrics and sales KPIs.

---

## 📊 Live Interactive Dashboard

- **Customer Shopping Behavior Dashboard:** [View on Tableau Public](https://public.tableau.com/app/profile/sravanthi.champatruni/viz/customerShoppingBehavior_17922647499530/CustomerTrendsDashboard) (revenue by category, age group, season, and subscription status)
- **Customer Trends Dashboard:** [View on Tableau Public](https://public.tableau.com/app/profile/sravanthi.champatruni/viz/CustomerTrendsBooksheet/CustomerTrendsDashboard) (KPI cards, customer funnel, demographic revenue, and product performance)

See the [`dashboard/`](dashboard/) folder for preview images.

---

## 🔍 Key Findings

Analysis of 3,900 retail transactions ($233,081 total revenue). The full write-up with strategy notes for each question is in [`reports/final_report.md`](reports/final_report.md).

- **Gender split:** Male customers generated $157,890 versus $75,191 from female customers, roughly two-thirds of total revenue.
- **Age groups:** Revenue is fairly even across segments, from $62,143 (Young Adult, highest) to $55,763 (Senior, lowest), so no single age group dominates.
- **Retention:** 3,192 customers (about 82%) are Loyal, 625 are Returning, and only 83 are New, showing a strong recurring customer base.
- **Discounts:** 839 customers used a promo discount and still spent above the average order value, so discounts do not always reduce basket size. Hat (50.00%) and Sneakers (49.66%) have the highest share of discounted purchases.
- **Subscriptions:** Subscribers and non-subscribers spend almost the same per transaction ($59.49 vs $59.87). Only 1,053 customers are subscribed, and 72.4% of repeat buyers (more than 5 previous purchases) have not subscribed.
- **Shipping:** Express shipping orders average $60.48 versus $58.46 for Standard.
- **Products:** Gloves, Sandals, Boots, Hat, and Skirt have the highest average review ratings (3.78 to 3.86). Jewelry, Blouse, and Pants lead on order volume (171 orders each).
- **Category revenue:** Clothing is the largest category at $104,264 (about 45% of revenue), followed by Accessories ($74,200), Footwear ($36,093), and Outerwear ($18,524).
- **Seasonality:** Revenue is steady all year, from $55,777 in Summer to $60,018 in Fall, so there is no strong seasonal swing.
- **Gender within age groups:** Male customers out-spend female customers in every age group, at roughly a 2:1 ratio (for example, $42,001 vs $20,142 among Young Adults).
- **Full-price top sellers:** Among purchases without a discount, Blouse ($6,916), Socks ($6,120), and Shirt ($5,979) bring in the most revenue.

### Recommendations

- Build targeted campaigns around the 839 high-spending discount users and test premium offers on them.
- Run a subscription conversion campaign aimed at repeat buyers who are not yet subscribed.
- Reduce broad discounting on Hats and Sneakers, and shift promotion budgets to slower-moving items.

---

## ⚙️ Prerequisites & Environment Setup

Before executing the data pipeline or reviewing the relational models, ensure you have the following software and libraries configured on your local system.

### 1. Data Engineering Environment (Python)

- **Distribution Manager:** Anaconda (recommended for environment isolation) or a standard Python 3.x installation.
- **Development Interfaces:** Jupyter Notebook or JupyterLab.
- **Core Libraries:** pandas, numpy, seaborn, matplotlib, and SQLAlchemy.

### 2. Relational Database Architecture (SQL)

- **Database Engine:** PostgreSQL (Version 14 or higher recommended).
- **Administration Tool:** pgAdmin 4 or an equivalent SQL database client.
- **Database Driver:** psycopg2 (installed via pip to facilitate Python-to-PostgreSQL connectivity).

### 3. Business Intelligence & Shell Tools

- **Data Visualization:** Tableau Desktop (or access via a web browser for Tableau Public).
- **Terminal Interface:** Git Bash or a native command-line interface configured with Git.

---

## 🛠️ Data Pipeline & Workflow

### 1. Data Cleaning & Feature Engineering (Python)

- Handled missing value distributions by imputing null review ratings using the localized median of each product category to prevent bias.
- Standardized inconsistent text schemas and reformatted columns into standard database snake_casing.
- Engineered consumer segment classifications (such as dynamic age groups) using quantile binning.
- Converted text-based frequencies into numeric fields mapping active purchase days.
- Set up database connection pipelines to load clean data frames into PostgreSQL via SQLAlchemy engines.

### 2. Deep Data Analysis (PostgreSQL)

- Managed multi-table joins, subqueries, and group aggregations to isolate spending behaviors.
- Analyzed macro revenue distributions comparing demographic behavior across gender tiers.
- Evaluated high-impact segments by filtering promotional discount users spending above the average purchase baseline.
- Tracked customer retention brackets by categorizing users into New, Returning, and Loyal lifecycles using conditional `CASE` expressions.
- Implemented advanced window functions (`ROW_NUMBER()`) to rank the top three high-volume products inside individual categories.

### 3. Business Intelligence Dashboard (Tableau)

- Developed custom worksheets to visually compare revenue streams and active transaction weights against age groups.
- Built dynamic visualization layouts tracking overall product sales maps by category.
- Implemented visual filtering elements enabling stakeholder drill-downs across gender profiles, subscription status, and shipping methods.

---

## 📁 Repository Structure

- 📁 **`dashboard/`** — Tableau workbook files and live dashboard publication links.
- 📁 **`data/`** — Directory for raw and processed retail consumer tracking datasets.
- 📁 **`notebooks/`** — Jupyter Notebooks documenting data validation, cleaning, and database loading.
- 📁 **`reports/`** — Formal business problem briefs and performance presentation decks.
- 📁 **`sql/`** — Optimized PostgreSQL query scripts engineered to extract analytical business insights.

---

## 📜 Project Origin & Academic Credits

- **Curriculum Reference:** This case study is built as a hands-on portfolio implementation following the core problem parameters outlined by tutor **Amlan Mohanty**.
- **Platform Enhancement:** While the baseline tutorial framework structured reporting layouts via Power BI, the complete reporting layer for this repository was independently migrated, customized, and deployed using **Tableau Desktop** to highlight multi-platform visualization skills.
