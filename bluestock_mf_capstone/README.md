# 📈 Bluestock Mutual Fund Analytics - Capstone Project

**Phases Completed:** `Day 1`, `Day 2`, `Day 3`, `Day 4`, `Day 5` & `Day 6`

## 🎯 Project Overview
This repository contains the completed Capstone Project for the **Bluestock Fintech Data Analytics Internship**. The goal of this project is to build an end-to-end Mutual Fund Analytics Platform using real-world public data from AMFI India and `mfapi.in`. 

This README documents the progressive completion of daily milestones, moving from raw data ingestion to structured data engineering, analytics, dynamic Power BI Dashboards, and advanced Python recommender systems.

---

## 🚀 Day 1: Data Ingestion, API Integration & Quality Validation

### 1. Project Architecture & Setup
- Initialized a standard data science folder structure (`data/raw`, `data/processed`, `notebooks`, `scripts`, `sql`, `dashboard`, `reports`).
- Set up a virtual environment and installed core dependencies listed in `requirements.txt` (Pandas, Requests, NumPy, etc.).

### 2. Static Data Ingestion
- Successfully loaded 10 extensive real-world CSV datasets provided by Bluestock (comprising 40 schemes, 4.5 years of NAV history, and 87K+ transaction rows).
- Evaluated dataset schemas, shapes, and data types to prepare for downstream transformation.

### 3. Live API Integration (Live NAV Fetcher)
- Developed an automated Python script (`scripts/live_nav_fetch.py`) to interact with the public `mfapi.in` REST API.
- Dynamically fetched live NAV data for 6 critical benchmark schemes:
  - *HDFC Top 100 Direct (125497)*
  - *SBI Bluechip (119551)*
  - *ICICI Bluechip (120503)*
  - *Nippon Large Cap (118632)*
  - *Axis Bluechip (119092)*
  - *Kotak Bluechip (120841)*

### 4. Initial Exploratory Data Analysis (EDA)
- Conducted preliminary exploration of the `01_fund_master.csv` dataset.
- Extracted and mapped unique Fund Houses, Categories, Sub-categories, and Risk Grades to understand the AMFI scheme code structure.

### 5. Data Quality & Validation
- Executed a strict validation protocol to ensure cross-dataset integrity.
- Confirmed a **100% match** by validating that every AMFI scheme code present in the `fund_master` dataset flawlessly aligns with the historical records in the `nav_history` dataset.

---

## 🛠️ Day 2: Data Cleaning & SQL Database Design

### 1. Data Cleaning Pipeline (Pandas)
- **NAV History:** Parsed dates, sorted records by scheme, removed duplicates, and implemented critical forward-filling (`ffill`) logic to handle missing NAV values during weekends and market holidays.
- **Transactions:** Standardized transaction types (SIP, Lumpsum, Redemption), validated positive investment amounts, fixed date formats, and filtered valid KYC statuses.
- **Scheme Performance:** Validated numeric return values, flagged risk anomalies (e.g., negative Sharpe ratios), and enforced acceptable expense ratio ranges.
- Exported all cleaned datasets to the `data/processed/` directory.

### 2. Database Schema Design
- Designed a professional analytical **Star Schema** with dimension tables (`dim_fund`, `dim_date`) and fact tables (`fact_nav`, `fact_transactions`, `fact_performance`, `fact_aum`).
- Authored strict DDL statements (`sql/schema.sql`) defining Primary Keys and Foreign Keys for data integrity.

### 3. Data Loading (SQLAlchemy)
- Created an automated Python pipeline using `SQLAlchemy` to generate a local SQLite database (`bluestock_mf.db`).
- Iteratively mapped, transformed, and loaded tens of thousands of processed records from Pandas DataFrames directly into the structured SQL tables.

### 4. Analytical SQL Queries
- Authored 10 business-critical SQL queries (`sql/queries.sql`) to extract insights such as:
  - Top 5 Fund Houses by AUM.
  - Average NAV trends per month.
  - Total SIP Amount by Year (YoY Growth).
  - Transaction volumes distributed by Fund Category.

### 5. Documentation
- Created a comprehensive Data Dictionary (`data_dictionary.md`) documenting all tables, columns, data types, and business logic to ensure project maintainability.

---

## 📊 Day 3: Exploratory Data Analysis & Business Insights

### 1. Time-Series Analysis
- Plotted the daily NAV trend for 40 schemes (2022-2026), successfully highlighting the 2023 bull run and 2024 market corrections using `Plotly`.
- Visualized monthly SIP inflow trends, dynamically annotating the all-time high of ₹31,002 Cr.
- Charted the mutual fund industry's folio count growth showing an increase from 13.26 Cr to 26.12 Cr.

### 2. Market Size & Category Analysis
- Developed grouped bar charts to analyze AUM growth by fund house, highlighting SBI's dominance (~12.5L Cr).
- Created a Seaborn heatmap to track net inflow intensity across different fund categories over time.
- Built a sector allocation donut chart showing heavy investments in the Banking, IT, and Pharma sectors.

### 3. Investor Demographics
- Analyzed the investor base using interactive pie charts to show age group distribution (majority 26-35) and gender split.
- Designed box plots to observe SIP ticket size distribution across different age groups.
- Mapped geographic distribution with horizontal bar charts for state-wise SIP contributions and a T30 vs B30 city tier breakdown.

### 4. Fund Performance Correlation
- Computed a pairwise correlation matrix of daily returns for 10 selected funds and visualized it using a Seaborn heatmap to understand scheme dependencies and market movement similarities.

### 5. Insights & Deliverables
- Documented **10 key EDA findings** bridging data visualizations with actionable business insights directly within the Jupyter Notebook (`03_EDA_Analysis.ipynb`).
- Exported 15+ interactive and static charts to the `reports/` directory for final presentation preparation.

---

## 📈 Day 4: Fund Performance Analytics

### 1. Return Calculations
- Computed **Daily Returns** for all 40 schemes and validated the normal distribution of returns.
- Calculated the **Compound Annual Growth Rate (CAGR)** for 1-Year, 3-Year, and 5-Year horizons.

### 2. Risk Metrics
- Calculated annualized return and volatility metrics.
- Computed the **Sharpe Ratio** (using a 6.5% risk-free rate) to measure risk-adjusted returns.
- Computed the **Sortino Ratio** focusing solely on downside risk.
- Identified the **Maximum Drawdown (MDD)** for each fund to assess maximum historical loss.

### 3. Alpha & Beta (Market Regression)
- Utilized `scipy.stats.linregress` to perform an OLS regression of fund returns against the market benchmark.
- Extracted annualized **Alpha** (excess return over market) and **Beta** (market volatility correlation).

### 4. Composite Fund Scorecard
- Built a robust 0-100 Fund Scorecard system by applying strategic weights:
  - 30% for 3Y CAGR
  - 25% for Sharpe Ratio
  - 20% for Alpha
  - 15% for Expense Ratio (Inverse)
  - 10% for Max Drawdown (Inverse)
- Ranked and identified the Top 10 mutual funds in the dataset based on this composite score.

### 5. Benchmark Comparison & Tracking Error
- Visualized the Top 5 best-performing funds against the Market Benchmark over a 3-year cumulative growth period.
- Computed the **Tracking Error** to measure how closely the funds follow the benchmark index.
- Exported analytical results (`alpha_beta.csv`, `fund_scorecard.csv`) and visualizations (`benchmark_comparison.png`) to the `reports/` directory.

---

## 📊 Day 5: Dashboard Development (Power BI)

### 1. Data Modeling & Connection
- Imported processed CSV files and benchmark indices into Power BI to construct a comprehensive, interactive data model.

### 2. Page 1: Industry Overview
- Designed dynamic KPI cards highlighting Total AUM (₹81L Cr), Monthly SIP Inflows (₹31K Cr), and Industry Folios (26.12 Cr).
- Visualized historical AUM growth trends and top 10 dominant fund houses.

### 3. Page 2: Fund Performance
- Built an interactive Risk vs. Reward scatter plot (Return vs. Volatility).
- Integrated the custom 0-100 Fund Scorecard as a sortable matrix.
- Created comparative NAV line charts with drill-through capabilities.

### 4. Page 3: Investor Analytics
- Visualized demographic insights including transaction volume by state and age-group SIP averages.
- Developed a Donut chart comparing SIP, Lumpsum, and Redemption distributions.

### 5. Page 4: SIP & Market Trends
- Developed a dual-axis chart correlating monthly SIP inflows with the Nifty 50 index movement.
- Built a Matrix Heatmap to track category-wise capital inflows over time.
- Implemented Top N filtering to showcase the most invested fund categories in FY25.

### 6. Deliverables
- Exported the finalized, branded dashboard as `bluestock_mf_dashboard.pbix`.
- Generated a comprehensive multi-page `Dashboard.pdf` and high-resolution PNG snapshots for final reporting.

---

## 🧠 Day 6: Advanced Analytics & Risk Metrics

### 1. Advanced Risk Metrics (VaR & CVaR)
- Computed **Historical Value at Risk (VaR)** at a 95% confidence interval to determine the maximum expected daily loss for each fund.
- Calculated **Conditional VaR (CVaR)** to measure the average loss in worst-case scenarios.
- Visualized the **90-Day Rolling Sharpe Ratio** for top 5 funds to observe dynamic changes in risk-adjusted returns over time.

### 2. Investor Behavioral Analytics
- **Cohort Analysis:** Grouped investors by their first transaction year (2024 vs. 2025). Discovered that while 2024 had higher total investments, the 2025 cohort showed a higher average SIP amount (₹13,505 vs ₹10,996).
- **SIP Continuation Risk:** Analyzed transaction gaps for investors with 6+ SIPs. Successfully flagged investors with average gaps exceeding 35 days as 'at-risk' for potential churn.

### 3. Sector Concentration Risk (HHI)
- Applied the **Herfindahl-Hirschman Index (HHI)** on portfolio holdings to assess sector concentration.
- Identified and visualized the Top 10 most concentrated (high-risk) funds, highlighting vulnerabilities to specific sector downturns.

### 4. Fund Recommendation System
- Built an interactive Python script (`scripts/recommender.py`) to simulate a robo-advisor.
- The system takes user **Risk Appetite (Low / Moderate / High)** as input and dynamically recommends the Top 3 mutual funds utilizing the Sharpe Ratio and matching risk grades.

---

## 📂 Repository Structure (Final)

```text
bluestock_mf_capstone/
├── data/
│   ├── raw/                 # Original CSVs + Live API fetched CSVs
│   ├── processed/           # Cleaned CSVs
│   └── db/                  # SQLite database (bluestock_mf.db)
├── notebooks/
│   ├── 01_data_ingestion.ipynb
│   ├── 02_data_cleaning.ipynb
│   ├── 03_EDA_Analysis.ipynb
│   ├── 04_Performance_Analytics.ipynb
│   └── 05_Advanced_Analytics.ipynb  # VaR, Cohort, HHI Analysis (Day 6)
├── scripts/
│   ├── live_nav_fetch.py    # mfapi.in REST API extraction
│   └── recommender.py       # Terminal-based Fund Recommender System (Day 6)
├── sql/
│   ├── schema.sql           # SQLite Star Schema DDL
│   └── queries.sql          # Analytical business queries
├── dashboard/               
│   └── bluestock_mf_dashboard.pbix # Final Power BI Dashboard
├── reports/                 # Exported PNG charts, CSV reports (Scorecards, VaR, HHI, Cohort), and PDFs
├── requirements.txt         # Project dependencies
├── data_dictionary.md       # Database schema definitions
└── README.md                # Project Documentation (Current File)