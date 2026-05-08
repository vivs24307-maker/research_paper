# research_paper
# 🌊 FloodOracle: Hoovinahole Catchment Flood Prediction & Spatial Risk System

An end-to-end Machine Learning framework for forecasting river water levels and mapping spatial flood risks in the Hoovinahole region. This system integrates decades of ground truth observational data with satellite-derived meteorology to build a highly accurate, deployable disaster management dashboard.

---

## 🎯 Project Overview
Flooding in dynamic catchments requires a highly responsive predictive model. Traditional physical models struggle with localized climate anomalies and require extensive topographical data. This project leverages an **XGBoost Regressor** to model the non-linear relationships between atmospheric inputs (like pressure, temperature, and wind) and hydrological outputs (river stage). 

Crucially, this model explicitly engineers the **"Sponge Effect"**—calculating the mathematical interaction between cumulative historical rainfall and current soil saturation to predict flash flooding before it happens.

---

## ✨ Key Features
* **Multi-Source Data Integration:** Synchronizes daily NASA POWER satellite meteorology with localized manual gauge observations (2001–2026).
* **MSL Data Anomaly Resolution:** Features a custom cleaning pipeline that filters out Mean Sea Level (MSL) inconsistencies to isolate pure relative river depth.
* **Monsoon-Aware Feature Engineering:** Utilizes time-lagged rainfall ($t-1$, $t-3$, $t-7$ days) and composite soil saturation risk scores.
* **Outlier Preservation:** Hydrological extremes (flood peaks) are strictly preserved without standard scaling, as they depict actual flood overflows essential for predictive training.
* **Spatial Risk Mapping:** Translates numerical AI predictions into an interactive geographical dashboard using Folium, providing severity alerts for specific low-lying topographical zones.

---

## 🛠️ Tech Stack & Libraries
* **Language:** Python 3.11+
* **Data Processing:** Pandas, NumPy
* **Machine Learning:** Scikit-Learn, XGBoost
* **Data Visualization:** Matplotlib, Seaborn, Plotly
* **Geospatial Mapping:** Folium, Branca

---

## 📂 Data Architecture
The model relies on 9 independent parameters gathered from two main streams:

1. **Observational Ground Truth (`.csv`):** * River Water Level (Target)
   * River Water Discharge
   * Rainfall
   * Relative Humidity
2. **NASA POWER Meteorological Data (`.csv`):**
   * Precipitation
   * Soil Wetness
   * Surface Pressure
   * Temperature
   * Wind Speed

---

## 🚀 Installation & Setup

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/yourusername/FloodOracle.git](https://github.com/yourusername/FloodOracle.git)
   cd FloodOracle
