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
- Dataset: japan_inbound_visitors_monthly.csv
- Time span: 1990 to 2025
- Frequency: Monthly
- Source: https://statistics.jnto.go.jp/graph/#graph--inbound--travelers--transition

Monthly data on the number of foreign visitors to Japan (JNTO), covering the period from 1990 to 2025.
Used for analyzing long-term trends and building a tourism demand forecasting model.

### 2. FRED of St.Louis
- USD/JPY Exchange Rate (DEXJPUS): https://fred.stlouisfed.org/graph/fredgraph.csv?id=DEXJPUS

### 3. BIS (Bank for International Settlements) Data Portal
- Dataset: BIS_REER_Japan.csv
- Time span: 1964-01 to 2026-03
- Frequency: Monthly
- Source: https://data.bis.org/topics/EER/BIS,WS_EER,1.0/M.R.N.JP  

Real Effective Exchange Rate (REER) for Japan.

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
