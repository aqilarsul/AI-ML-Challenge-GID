# AIESEC MC India Analytics: 2026 Forecast Model

## 📌 Project Overview
This repository contains the solution for the AIESEC AI/ML Engineer application challenge. The goal is to analyze application data for **MC India** (2022-2025) and predict high-activity months for the year **2026**.

## 🚀 Approach & Methodology

### 1. Data Ingestion
- **Source:** AIESEC Analytics API (`https://analytics.api.aiesec.org/v2/applications/analyze.json`)
- **Method:** Iterative fetching of application data filtered by `home_office_id` (MC India) and date ranges.
- **Handling:** Data is cleaned and aggregated into monthly time-series buckets.

### 2. Modeling Strategy
- **Model:** Random Forest Regressor (Ensemble Learning).
- **Why this model?**
  - Unlike linear regression, Random Forest effectively captures **non-linear seasonality** (e.g., Summer/Winter peaks).
  - It is robust against outliers and requires less strict stationarity in the time-series data compared to ARIMA/SARIMA for this scale of data.
- **Features Used:** `Month`, `Quarter`, `Year`, `Lag_12` (Previous year's volume).

### 3. Results (2026 Forecast)
Based on the historical trends (2022-2025), the model predicts the following high-activity periods for 2026:
- **Peak 1:** [Month, e.g., May 2026] (Projected: X Apps)
- **Peak 2:** [Month, e.g., June 2026] (Projected: Y Apps)
- **Peak 3:** [Month, e.g., January 2026] (Projected: Z Apps)

*Complete data is available in `data/mc_india_forecast_2026.csv`.*

## 🛠️ Installation & Usage

1. **Clone the repository**
   ```bash
   git clone [https://github.com/your-username/AIESEC-MC-India-Analytics.git](https://github.com/your-username/AIESEC-MC-India-Analytics.git)
