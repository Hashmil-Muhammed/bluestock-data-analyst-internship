# 📈 Bluestock Mutual Fund Analytics - Capstone Project

**Phase:** `Day 1: Data Ingestion, API Integration & Quality Validation`

## 🎯 Project Overview
This repository contains the ongoing Capstone Project for the **Bluestock Fintech Data Analyst Internship**. The goal of this project is to build an end-to-end Mutual Fund Analytics Platform using real-world public data from AMFI India and `mfapi.in`. 

This specific README documents the completion of **Day 1 tasks**, which focus on establishing a robust Data Engineering and ETL foundation.

---

## 🚀 Day 1 Milestones Achieved

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

## 📂 Repository Structure (As of Day 1)

```text
bluestock_mf_capstone/
├── data/
│   └── raw/                   # Contains 10 original CSVs + Live API fetched CSVs
├── notebooks/
│   └── 01_data_ingestion.ipynb # Initial EDA and data validation notebook
├── scripts/
│   └── live_nav_fetch.py       # Python script for mfapi.in REST API extraction
├── requirements.txt            # Project dependencies
└── README.md                   # Day 1 Documentation
