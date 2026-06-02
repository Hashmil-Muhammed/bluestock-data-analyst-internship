# Bluestock Fintech Data Analyst Internship Portfolio

Welcome to my Data Analyst Internship workspace! This repository contains all the projects, weekly assignments, and the final capstone work completed during my intensive 2-week internship at **Bluestock Fintech**. 

It serves as a comprehensive portfolio showcasing end-to-end data pipelines, exploratory data analysis (EDA), and data visualization tasks focused on the Indian Mutual Fund industry.

## 🚀 Internship Roadmap & Progress

### 🟢 Week 1: Intensive Learning Phase (Completed)
During the first week, I underwent rigorous training in data analytics, database management, and fintech concepts. The daily milestones achieved were:

* **Day 1 (Python Foundation):** Environment setup, Python basics, and Object-Oriented Programming (OOP). Wrote a Python script to extract and analyze statistics from financial CSVs.
* **Day 2 (Data Manipulation):** Mastered NumPy (arrays, operations) and Pandas (DataFrames, data cleaning). Completed an Exploratory Data Analysis (EDA) notebook on financial data.
* **Day 3 (SQL & Databases):** Learned SQL fundamentals, CTEs, Window Functions, and set up PostgreSQL using pgAdmin. The Capstone project was officially assigned.
* **Day 4 (Data Viz & APIs):** Explored Matplotlib and Seaborn for data storytelling. Built REST APIs using Flask and connected them to PostgreSQL via psycopg2.
* **Day 5 (Fintech & ML Basics):** Studied stock market mechanics (OHLC, yfinance) and Mutual Funds (NAV, CAGR, SIP). Introduced to Machine Learning basics and reached 50% completion of the Capstone project.

### 🟡 Week 2: Capstone Execution & Testing (Current Phase: Week 2, Day 1)
*I am currently on Week 2, Day 1 of the program.* This week focuses entirely on the Prerequisite Test preparation and the final polishing of the Capstone Project.

#### 📌 Current Capstone Project: Mutual Fund Analytics 
**Phase 1: Data Ingestion & Quality Validation (Completed)**
* Loaded and explored 10 extensive CSV datasets containing Mutual Fund historical data.
* Developed a Python script (`live_nav_fetch.py`) to connect with the `mfapi.in` REST API and dynamically fetch live NAV data for 6 key schemes (including HDFC Top 100, SBI Bluechip, etc.).
* Performed Exploratory Data Analysis (EDA) on the `fund_master` dataset to understand fund houses, categories, and risk grades.
* Executed rigorous data validation to ensure cross-dataset consistency (mapping AMFI codes between `fund_master` and `nav_history`).

## 📂 Repository Structure
The workspace is organized into a standard data science project structure:

* **`data/`**: Contains all datasets used in the projects.
    * `raw/`: Immutable original data and live data fetched via APIs.
    * `processed/`: Cleaned and transformed datasets ready for analysis.
* **`notebooks/`**: Jupyter notebooks for Exploratory Data Analysis (EDA) and step-by-step documentation.
* **`scripts/`**: Python scripts for automated tasks (e.g., API data fetching).
* **`sql/`**: SQL scripts for database creation and queries.
* **`dashboard/`**: Power BI / Tableau dashboard files.
* **`reports/`**: Final project reports, summaries, and presentations.

## 🛠️ Tech Stack & Tools
* **Language:** Python
* **Libraries:** Pandas, Requests, NumPy, Matplotlib, Seaborn
* **APIs & Backend:** `mfapi.in`, Flask
* **Database:** PostgreSQL (pgAdmin 4)
* **Version Control:** Git & GitHub

## 💡 How to Run the Code
1. Clone this repository:
   ```bash
   git clone [https://github.com/Hashmil-Muhammed/bluestock-data-analyst-internship.git](https://github.com/Hashmil-Muhammed/bluestock-data-analyst-internship.git)
2. Install the required dependencies
Bash
pip install -r requirements.txt
Run the live NAV fetcher script:
3.Run the live NAV fetcher script:
Bash
python scripts/live_nav_fetch.py
📬 Contact
Hashmil Muhammed Email: hashmilmuhammedparammal@gmail.com
GitHub: @Hashmil-Muhammed
