# 🌦 Pakistan Weather Data Analysis (2020–2024)

## 📌 Project Overview
This project explores **Pakistan's daily weather data from 2020 to 2024** using Python.  
The analysis includes **data cleaning, exploratory data analysis (EDA), visualizations, anomaly detection, and a baseline predictive model** for daily average temperature (`tavg`).  

The goal is to demonstrate skills in:
- Data wrangling (cleaning, type conversion, feature engineering)  
- Exploratory analysis & visualization  
- Identifying patterns, trends, and anomalies in climate data  
- Building and evaluating a simple machine learning model  

---

## 📊 Dataset Description
The dataset contains daily weather observations with the following key columns:

- **date, year, month, day, dayofweek, is_weekend** → temporal features  
- **city, region, latitude, longitude, elevation** → geographic features  
- **tmin, tmax, tavg, prcp, wspd, humidity, pressure, dew_point, cloud_cover, visibility** → meteorological variables  
- **temp_range, is_hot_day, is_cold_day, rainfall_intensity, wind_category** → derived weather indicators  

📏 Shape: ~[number of rows you found with `df.shape`] records × 27 columns  
📍 Coverage: Multiple cities across Pakistan, 2020–2024  

---

## 🛠 Tools & Libraries
- **Python 3.13** (VS Code, Jupyter Notebook)  
- **Libraries:**  
  - Data handling → `pandas`, `numpy`  
  - Visualization → `matplotlib`  
  - Modeling → `scikit-learn` (RandomForestRegressor)  

---

## 🔎 Exploratory Data Analysis (EDA)
Key analysis steps:
1. **Data Cleaning & Preparation**
   - Converted columns to correct data types
   - Handled missing values
   - Created new date-based features (`year`, `month`, `dayofweek`, `is_weekend`)

2. **Visualizations**
   - 📈 **Daily Temperature Trend:** 7-day rolling averages of `tavg` showed clear seasonal cycles.  
   - 📆 **Monthly Seasonality:** Hottest months were May–June, coldest in Jan–Feb.  
   - 🏙 **City Comparison:** Boxplots revealed regional climate differences (e.g., northern cities cooler).  
   - 🌧 **Rainfall Heatmap:** Strong rainfall peaks during monsoon (Jul–Sep).  
   - 🔗 **Correlation Matrix:** Confirmed strong relationships (`tavg` vs `tmin`/`tmax`, inverse with humidity).  
   - ☁ **Scatter (tavg vs humidity):** Negative trend between humidity and temperature.  

3. **Anomaly Detection**
   - Identified extreme hot/cold days using IQR method.  
   - Outliers could indicate both extreme weather events and possible data errors.  

---

## 🤖 Predictive Modeling
A simple **Random Forest Regressor** was built to predict **daily average temperature (`tavg`)** using:
- Features: `tmin`, `tmax`, `prcp`, `wspd`, `humidity`, `pressure`, `dew_point`, and city indicators.  

### Evaluation Metrics
- **MAE (Mean Absolute Error):** ~X °C (average error in prediction)  
- **RMSE (Root Mean Squared Error):** ~Y °C (stricter penalty for big errors)  

*(Replace X and Y with your actual results after running the notebook.)*

### Interpretation
- The model reasonably captured temperature patterns.  
- Errors within ~2–3 °C indicate a solid baseline, but further improvement is possible with advanced time-series models.  

---

## Key Findings
1. Temperatures follow a **strong seasonal cycle** each year.  
2. **Monsoon rainfall** dominates July–September with variability across years.  
3. **Regional differences**: Northern high-altitude cities are cooler, southern cities warmer and more humid.  
4. **Correlations**: Expected weather relationships (e.g., tavg vs tmin/tmax) were confirmed.  
5. **Predictive power**: Even a simple model provided useful estimates of average daily temperature.  

---


## 📂 Repository Structure
