# 🌍 Global Weather Analysis & Forecasting
### PMA-AI Bootcamp Cohort 9 — Assessment 2 (Data Science Track)
**Applicant:** Zona Zubair | **Role Applied:** Fullstack + Data Science

---

## 📌 About PM Accelerator

> PM Accelerator's mission is to empower aspiring and experienced product managers through immersive, real-world training programs. We bridge the gap between theory and practice by providing mentorship, hands-on projects, and community-driven learning — helping members land top product roles and grow as leaders in tech.

---

## 📋 Project Overview

This project is a complete end-to-end data science pipeline built on the **Global Weather Repository** dataset from Kaggle. The dataset contains daily weather observations for cities worldwide, with 40+ features including temperature, humidity, precipitation, air quality, wind speed, and more.

The notebook covers the full data science workflow — from raw data cleaning to advanced forecasting — with every decision explained in plain language.

---

## 🎯 What This Notebook Does

| Section | What it covers |
|---|---|
| Data Cleaning | Missing values, outlier capping, date parsing, deduplication |
| EDA | Distributions, time trends, correlations, country comparisons |
| Anomaly Detection | Isolation Forest — flags statistically unusual weather events |
| Climate Analysis | Long-term seasonal patterns by month and region |
| Environmental Impact | Air quality vs. weather variable correlations |
| Feature Importance | Random Forest + Permutation Importance (two-method comparison) |
| Spatial Analysis | Interactive global temperature maps (Plotly) |
| ARIMA Forecasting | Classical statistical time-series model (baseline) |
| Prophet Forecasting | Meta's seasonal-aware Bayesian forecasting model |
| Ensemble Model | Weighted average of ARIMA + Prophet |
| Model Comparison | MAE/RMSE table + bar chart across all three models |

---

## 📂 Repository Structure

```
weather-analysis-ds/
│
├── weather_analysis.ipynb        # Main Colab notebook (full pipeline)
└── README.md                     # This file
```

---

## 📊 Dataset

**Name:** Global Weather Repository  
**Source:** [Kaggle — nelgiriyewithana/global-weather-repository](https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository)  
**Key features:** temperature, humidity, wind, pressure, precipitation, air quality, lat/lon

> ⚠️ Dataset not included in this repo due to size. Download from Kaggle link above.

---

## 🛠️ Tech Stack

| Tool | Purpose |
|---|---|
| Python 3.10 | Core language |
| Pandas / NumPy | Data manipulation |
| Matplotlib / Seaborn | Static visualizations |
| Plotly | Interactive maps |
| Scikit-learn | Isolation Forest, Random Forest, feature importance |
| Statsmodels | ARIMA, ADF test, ACF/PACF |
| Prophet (Meta) | Seasonal forecasting |
| Google Colab | Notebook environment |

---

## 🚀 How to Run

1. Download `GlobalWeatherRepository.csv` from [Kaggle](https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository)
2. Upload it to Google Drive at: `My Drive/GlobalWeatherRepository.csv`
3. Open `weather_analysis.ipynb` in Google Colab
4. In Section 2, update `DATA_PATH` to match your Drive path
5. Run all cells: `Runtime → Run all`

---

## 📈 Key Results

### Forecasting Model Comparison (30-Day Forecast)

| Model | MAE (°C) | RMSE (°C) |
|---|---|---|
| ARIMA(2,1,2) | see notebook | see notebook |
| Prophet | see notebook | see notebook |
| **Weighted Ensemble** | **🏆 Best** | **🏆 Best** |

### Key Findings
- ~3% of readings flagged as anomalies (extreme events / sensor errors)
- Equatorial countries: minimal seasonal variation. Temperate regions: strong cycles
- Air quality worsens during high-temperature, low-wind conditions
- Ensemble consistently outperformed both individual models

---

## 🧠 Why These Modeling Choices?

**Isolation Forest** — handles multi-dimensional weather data without assuming a distribution. Better than simple z-score thresholds.

**ARIMA(2,1,2)** — p=2, q=2 selected from ACF/PACF plots; d=1 confirmed by ADF stationarity test. Serves as a strong interpretable baseline.

**Prophet** — automatically detects yearly/weekly seasonality without manual tuning. Robust to missing values and outliers.

**Weighted Ensemble** — weights each model by inverse MAE. Lower error = higher trust. Simple, transparent, and outperforms both models alone.

---
