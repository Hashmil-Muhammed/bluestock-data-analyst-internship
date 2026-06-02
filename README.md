# Bluestock Fintech Data Analyst Internship Portfolio

Welcome to my Data Analyst Internship workspace! This repository contains all the projects, weekly assignments, and the final capstone work completed during my internship at **Bluestock Fintech**. 

It serves as a comprehensive portfolio showcasing end-to-end data pipelines, exploratory data analysis (EDA), and data visualization tasks focused on the Indian Mutual Fund industry.

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
* **Libraries:** Pandas, Requests, Jupyter, NumPy
* **APIs:** `mfapi.in` (For fetching live mutual fund NAV data)
* **Version Control:** Git & GitHub

## 🚀 Project Milestones & Progress

### 📌 Capstone Project: Mutual Fund Analytics
**Phase 1: Data Ingestion & Quality Validation (Completed)**
* Loaded and explored 10 extensive CSV datasets containing Mutual Fund historical data.
* Developed a Python script (`live_nav_fetch.py`) to connect with the `mfapi.in` REST API and dynamically fetch live NAV data for 6 key schemes (including HDFC Top 100, SBI Bluechip, etc.).
* Performed Exploratory Data Analysis (EDA) on the `fund_master` dataset to understand fund houses, categories, and risk grades.
* Executed rigorous data validation to ensure cross-dataset consistency (mapping AMFI codes between `fund_master` and `nav_history`).

*(More phases will be updated as the internship progresses...)*

## 💡 How to Run the Code
1. Clone this repository:
   ```bash
   git clone [https://github.com/Hashmil-Muhammed/bluestock-data-analyst-internship.git](https://github.com/Hashmil-Muhammed/bluestock-data-analyst-internship.git)
