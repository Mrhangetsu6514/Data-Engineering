# 🏙️ Tel Aviv Real Estate Data Pipeline

An automated Data Engineering pipeline that scrapes, cleans, and analyzes rental market data from Tel Aviv. This project transforms unstructured web data into verified, de-duplicated insights stored in a time-series format.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]((https://colab.research.google.com/drive/1TdRN-RxvRoT_AplfdB9rLfmOfIr8BRbx?usp=sharing))

## 🚀 Overview
Finding an apartment in Tel Aviv is a data challenge. This pipeline was built to track real-time market shifts by scraping listing sites, applying statistical confidence models, and maintaining a clean dataset on GitHub.

## 🛠️ Tech Stack
- **Language:** Python 3.x
- **Automation:** Selenium (Web Scraping)
- **Data Processing:** Pandas, NumPy
- **Statistics:** SciPy (Margin of Error / Confidence Intervals)
- **Security:** MD5 Hashing (for unique ID generation)
- **Storage:** CSV / GitHub Version Control

## 🧠 Key Features
- **Dynamic Multi-Page Scraping:** Automatically navigates through pagination until a significant sample size (n > 30) is reached.
- **Data Integrity (Surrogate Keys):** Generates a unique MD5 hash for every listing based on `Neighborhood + Price + Rooms` to prevent duplicate counts from "promoted" ads.
- **Statistical Confidence Score:** Calculates an accuracy percentage based on price variance, helping to identify if a neighborhood's average is reliable or highly volatile.
- **Automated Cleaning:** Filters out "outlier" data (e.g., parking spots listed as apartments or fake luxury listings).

## 📊 Sample Output
| Neighborhood | Price (NIS) | Rooms | SQM | Price/SQM |
| :--- | :--- | :--- | :--- | :--- |
| Lev Ha'ir | 13,000 | 4.0 | 70 | 185.7 |
| Sarona | 12,000 | 4.0 | 119 | 100.8 |

## 📈 Market Metrics Provided
- **Average Market Rent** (with 95% Confidence Interval)
- **Market Spread** (Gap between Min/Max listings)
- **Neighborhood Supply Tracking**

## 🏗️ Next Steps
- [ ] Implement GitHub Actions to automate daily scrapes.
- [ ] Connect data to a PowerBI or Tableau dashboard.
- [ ] Expand scraping logic to include Ramat Gan and Givatayim.

---
*Disclaimer: This project is for educational purposes only.*
