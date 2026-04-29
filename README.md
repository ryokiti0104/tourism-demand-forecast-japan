# Tourism Demand Forecast for Japan
### Forecasting inbound tourism demand using macroeconomic indicators and search trends

![Python](https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54)
![Pandas](https://img.shields.io/badge/pandas-%23150458.svg?style=for-the-badge&logo=pandas&logoColor=white)
![Statsmodels](https://img.shields.io/badge/statsmodels-blue?style=for-the-badge)

## Overview
This project analyzes and forecasts monthly inbound tourism demand to Japan using a time-series model.

## Data Sources
### 1. JNTO (Foreign Visitors to Japan, Tourism Consumption)
##### (Access to the JNTO website may be restricted if you open it directly from GitHub)
Monthly data on the number of foreign visitors to Japan (JNTO), covering the period from 1990 to 2025.
- Dataset: japan_inbound_visitors_monthly.csv
- Time span: 1990 to 2025 + 2026-01
- Frequency: Monthly
- Source: https://statistics.jnto.go.jp/graph/#graph--inbound--travelers--transition

### 2. FRED of St.Louis
USD/JPY Exchange Rate (DEXJPUS).
- Time span: 1971-01-04 to 2026-04-24
- Frequency: Daily
- Source: https://fred.stlouisfed.org/graph/fredgraph.csv?id=DEXJPUS

### 3. BIS (Bank for International Settlements) Data Portal
Real Effective Exchange Rate (REER) for Japan.
- Dataset: BIS_REER_Japan.csv
- Time span: 1964-01 to 2026-03
- Frequency: Monthly
- Source: https://data.bis.org/topics/EER/BIS,WS_EER,1.0/M.R.N.JP

### 4. Google Trends
This dataset contains monthly Google Trends search interest indices from January 2004 to April 2026 for travel-related keywords, including “Japan Travel”, “France Travel”, “Spain Travel”, “America Travel”, and “World Travel”. These indices (scaled from 0 to 100) reflect relative search popularity over time and serve as a proxy for global tourism interest and travel demand.
- Dataset: google_trends.csv
- Time span: 2004-01 to 2026-04
- Frequency: Monthly
- Source: https://trends.google.co.jp/trends/

### 5. Japan Tourism Agency (観光庁)
This dataset is based on the official `Lodging Travel Statistics` published by the Japan Tourism Agency (JTA).  
It covers approximately 18 years of monthly data from January 2007 to December 2025, providing a long-term view of accommodation demand in Japan.

- Dataset: Excel Data
- Time span: 2007-01 to 2025-12
- Frequency: Monthly
- Source: https://www.mlit.go.jp/kankocho/tokei_hakusyo/shukuhakutokei.html

The dataset includes the following key indicators:

- **Total Guest Nights (`total_guest_nights`)**  
  Total number of guest nights (both domestic and international)

- **Foreign Guest Nights (`foreign_guest_nights`)**  
  Number of guest nights by international visitors (inbound tourism demand)

## Methodology

The forecasting model uses **SARIMAX (Seasonal ARIMA with exogenous variables)**.

SARIMAX was chosen because:

- Tourism demand has **strong seasonality**
- Exchange rates and search trends can be included as **exogenous variables**
- It is widely used in **economic time-series forecasting**

Model inputs include:

- Lagged visitor arrivals
- Exchange rate indicators
- Google search trends

---


## Visualization
### Visitor Arrivals

![visitor arrivals](outputs/monthly_inbound_visitors.png)

Inbound tourism to Japan shows strong growth before COVID-19 and a sharp decline during the pandemic.

---

### Seasonal Pattern of Visitor Arrivals

![seasonality](outputs/seasonality_of_tourism_demand.png)

Inbound tourism demand shows clear seasonal patterns, indicating that monthly arrivals are not evenly distributed throughout the year.

---

### Exchange Rate Indicators

![exchange rate](outputs/exchange_rate.png)

Exchange rate movements can affect travel affordability and may influence inbound demand.

---

## Conclusion

![forecast](outputs/tourism_demand_forecast2.png)

The SARIMAX model captures the seasonal pattern of inbound tourism and produces reasonable forecasts when macro indicators are included.

This suggests that combining economic indicators and search trends may help improve tourism demand forecasting.

---

Author
Ryo Kawada
