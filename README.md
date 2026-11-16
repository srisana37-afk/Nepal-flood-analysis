
# 🌊 Nepal Flood & River Discharge Prediction

## 📌 Project Overview

This project focuses on analyzing hydrological and meteorological data from Nepal (2023–2026) using **Python** for Exploratory Data Analysis (EDA) and **Machine Learning** to forecast next-day river discharge (`river_discharge_m3s`). The objective is to uncover environmental patterns driving flood risks across major river basins and build predictive regression models to support early flood warning systems.

The project demonstrates how data analytics and machine learning can transform raw weather and river station data into actionable insights for disaster preparedness.

---

## 🎯 Objectives

- Perform data cleaning, missing value checks, and type verification.
- Conduct Exploratory Data Analysis (EDA) across river stations, basins, and weather variables.
- Engineer time-series target variables to predict next-day river discharge.
- Train and compare multiple Machine Learning regression models (Random Forest, Linear Regression, Decision Tree).
- Evaluate model performance using MAE, RMSE, and $R^2$ metrics.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Google Colab 

---

## 📁 Project Structure

Nepal-Flood-Prediction/
├── CORRECTED_2023_2026_NEPAL_FLOOD_WEATHER_KAGGLE.csv   # Dataset
├── nepal_flood_prediction.ipynb                         # Python EDA & ML Notebook
└── README.md                                            # Project Documentation


## 📂 Dataset Description

The dataset contains 13,390 daily hydrological and meteorological observations across Nepal's river stations (2023–2026), 

including:

- `date` — Observation date
- `location` — Monitoring station location (e.g., Rasuwagadhi, Chisapani, Devghat, Khokana, Kusum)
- `river` — River name (e.g., Bhote Koshi, Karnali, Narayani, Bagmati, West Rapti)
- `basin` — River basin (e.g., Narayani, Karnali, Bagmati, Rapti)
- `dhm_station` — Department of Hydrology and Meteorology station ID
- `latitude` & `longitude` — Geographic coordinates of the station
- `elevation_m` — Station elevation in meters
- `precipitation_mm` & `precipitation_hours` — Daily precipitation volume and duration
- `rain_mm` — Rainfall measurement in millimeters
- `soil_moisture_0_100cm_m3m3` — Volumetric soil moisture (0–100 cm depth)
- `temperature_mean_c` & `dew_point_mean_c` — Mean air temperature and dew point (°C)
- `relative_humidity_mean_pct` — Mean relative humidity (%)
- `wind_speed_max_kmh`, `wind_gusts_max_kmh`, `wind_direction_dominant_deg` — Wind metric
- `river_discharge_m3s` — Daily river discharge rate ($m^3/s$)

---

## 🧹 Data Preprocessing

The following preprocessing steps were performed:

- Checked for missing values across all 19 columns (verified zero null entries).
- Verified data types for numerical (`float64`, `int64`) and categorical (`object`) features
- Created the next-day target variable (`target_next_discharge`) by shifting `river_discharge_m3s` by `-1`
- Dropped rows with missing target values resulting from the time shift.
- Selected numerical features and performed an 80/20 train-test split.

---

## 📈 Exploratory Data Analysis & Modeling

The notebook includes analysis and modeling of:

- Station-wise and basin-wise river discharge distributions
- Relationship between precipitation, soil moisture, and river discharge
- Model training and comparison using:
  - **Random Forest Regressor** (`n_estimators=50`, baseline $R^2$: `0.7051`, MAE: `10.01`, RMSE: `31.91`)
  - **Linear Regression**
  - **Decision Tree Regressor**

---    https://github.com/srisana37-afk/Nepal-flood-analysis/blob/main/Doc1.docx          

## 🔍 Key Insights

- Weather and hydrological indicators (such as precipitation, soil moisture, and station elevation) explain over **70%** of the variance in next-day river discharge using a baseline Random Forest model
- 
- Multi-station time-series data requires station-level grouping (`groupby('location')`) prior to shifting targets to prevent cross-station leakage

- High-elevation and monsoon-affected basins exhibit sharper discharge spikes during sustained precipitation hours


---

## ▶️ How to Run the Project

### 1. Clone the Repository

https://github.com/srisana37-afk/Nepal-flood-analysis


2. Install Required Libraries

pip install pandas numpy scikit-learn matplotlib seaborn


3. Open the Notebook

    google colab nepal_flood_prediction

(https://github.com/srisana37-afk/Nepal-flood-analysis/blob/main/nepal-flood40.ipynb)

📌 Results

The project successfully demonstrates:


   Data inspection, null verification, and time-series target engineering   Predictive modeling of river discharge using Scikit-learn regressors   Quantitative evaluation using MAE, RMSE, and $R^2$   These analyses help researchers and disaster management teams anticipate high-discharge events and monitor flood-prone river basins.


🚀 Future Enhancements


Add lag features (1-day, 3-day, and 7-day rolling precipitation and discharge)   Implement chronological date-based train/test splitting per station   Build an interactive Power BI dashboard to visualize basin-level flood risk   Experiment with gradient boosting models (XGBoost, LightGBM) and hyperparameter tuning   


---

## 📚 References

- Python Documentation: https://docs.python.org/
- Pandas Documentation: https://pandas.pydata.org/
- NumPy Documentation: https://numpy.org/
- Scikit-learn Documentation: https://scikit-learn.org/stable/
- Matplotlib Documentation: https://matplotlib.org/
- Seaborn Documentation: https://seaborn.pydata.org/

---

## 👩‍💻 Author

**Rizana Sherin**

Nepal Flood & River Discharge Prediction using Python & Machine Learning
