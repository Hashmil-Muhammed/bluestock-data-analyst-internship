# 📈 Bluestock Mutual Fund Analytics - Capstone Project

**Phases Completed:** `Day 1` & `Day 2`

## 🎯 Project Overview
This repository contains the ongoing Capstone Project for the **Bluestock Fintech Data Analyst Internship**. The goal of this project is to build an end-to-end Mutual Fund Analytics Platform using real-world public data from AMFI India and `mfapi.in`. 

This README documents the progressive completion of daily milestones, moving from raw data ingestion to structured data engineering and analytics.

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

## 📂 Repository Structure (Updated: Day 2)

```text
bluestock_mf_capstone/
├── data/
│   ├── raw/                 # 10 original CSVs + Live API fetched CSVs
│   ├── processed/           # Cleaned CSVs (nav_history, transactions, performance)
│   └── db/                  # SQLite database (bluestock_mf.db)
├── notebooks/
│   ├── 01_data_ingestion.ipynb # Initial EDA and data validation
│   └── 02_data_cleaning.ipynb  # Data cleaning & SQLAlchemy DB loading
├── scripts/
│   └── live_nav_fetch.py       # Python script for mfapi.in REST API extraction
├── sql/
│   ├── schema.sql           # SQLite Star Schema DDL statements
│   └── queries.sql          # 10 Analytical business queries
├── requirements.txt         # Project dependencies
├── data_dictionary.md       # Database schema and business definitions
└── README.md                # Project Documentation (Current File)
