# ⚙️ Scripts Directory: Automation & Applications

This directory shifts the project from static analysis to automated software engineering. It contains modular, standalone Python scripts.

## 📂 Directory Structure

```text
📦scripts
 ┣ 📜live_nav_fetch.py
 ┣ 📜recommender.py
 ┗ 📜README.md
```

## 🚀 Application Details

### 1. live_nav_fetch.py (Automated API Extraction)

A robust data extraction script that interfaces with the public mfapi.in REST API.

**Function:** Dynamically fetches real-time NAV data for 6 critical benchmark funds.

**Features:** Includes error handling, JSON parsing, and automated saving directly into the `data/raw/` pipeline.

---

### 2. recommender.py (Robo-Advisor Simulation)

An interactive Command Line Interface (CLI) application that recommends mutual funds based on quantitative metrics.

**Algorithm:** Prompts the user for a Risk Appetite (Low/Moderate/High). It dynamically maps this input against standard risk categories, filters the dataset, and ranks the results using the pre-calculated Sharpe Ratio to guarantee optimal risk-adjusted returns.

### Usage

```bash
python scripts/recommender.py
```