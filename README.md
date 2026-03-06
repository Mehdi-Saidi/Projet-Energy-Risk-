#  Electricity Load Forecasting in France

Machine learning and time series project developed at **ENSAE** to forecast **hourly electricity demand in France** using historical consumption and weather data.

The goal is to understand the temporal dynamics of electricity demand and evaluate different forecasting models.

---

#  Problem Statement

Electricity demand forecasting is essential for maintaining the **balance of the electrical grid**.

Short-term demand depends on several factors:

- daily and weekly consumption patterns
- seasonal effects
- weather conditions, especially **temperature**

This project aims to build and compare several models to **predict hourly electricity load in France**.

---

#  Dataset

The dataset combines two main data sources.

### Electricity consumption

- Source: **RTE / ODRÉ**
- Hourly electricity consumption in France
- Unit: **Megawatts (MW)**

### Weather data

- Source: **Météo-France SYNOP archives**
- Hourly temperature observations
- Weather station: **Orly**

Temperature data originally recorded every 3 hours were **interpolated to obtain hourly values**.

---

#  Data Preparation

Several preprocessing steps were performed:

### Data cleaning
- Handling missing values
- Aggregation to hourly frequency

### Time alignment
- Synchronization of electricity consumption and temperature

### Dataset merging
Final dataset includes: load_mw, temperature, datetime 

The dataset covers the period: 2020 – 2023

---

#  Exploratory Data Analysis (EDA)

The exploratory analysis focuses on identifying the main patterns in electricity consumption.

Key observations include:

- strong **daily consumption cycles**
- **weekly seasonality**
- higher consumption during **cold temperatures**
- clear **seasonal patterns**

Visualization techniques include:

- time series plots
- seasonal decomposition
- correlation analysis between load and temperature

---

#  Baseline Model

A **persistence model** was used as a baseline.

The persistence model assumes:
Load(t) = Load(t-1)

This simple benchmark allows comparison with more advanced forecasting methods.

---

#  Forecasting Models

Several models were implemented and compared.

### Linear Regression

A regression model using **calendar variables**:

- hour of day
- day of week
- seasonal indicators
- temperature

This model captures deterministic temporal patterns.

---

### SARIMAX

Seasonal ARIMA model with **exogenous variables (temperature)**.

Advantages:

- captures temporal dependencies
- models seasonal patterns
- incorporates external variables

---

### ETS (Holt-Winters)

Exponential smoothing model designed for time series with:

- trend
- seasonality

Useful for modeling structured temporal signals.

---

#  Evaluation Metrics

Model performance was evaluated using:

### MAE (Mean Absolute Error)

Average absolute difference between predicted and observed values.

### RMSE (Root Mean Squared Error)

Penalizes larger prediction errors.

These metrics allow comparison between forecasting models.

---

#  Results

The models show different strengths:

- **Linear regression** captures calendar effects
- **SARIMAX** captures temporal dynamics and temperature impact
- **ETS** performs well on seasonal structures

Combining temperature and time-based variables significantly improves forecasting accuracy.

---

#  Key Insights

The analysis highlights several important drivers of electricity consumption:

### Weather effects
- temperature strongly influences electricity demand

### Temporal patterns
- daily cycles
- weekly patterns
- seasonal variations

These factors are essential for accurate short-term load forecasting.

---

#  Possible Improvements

Future improvements could include:

- adding **more weather variables** (wind, humidity, solar radiation)
- integrating **holiday indicators**
- using **advanced ML models** (Gradient Boosting, LSTM)
- incorporating **regional electricity demand**

---

#  Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn
- Jupyter Notebook

---

# 👨‍💻 Author

Project developed at **ENSAE**

Mehdi Saidi
Hugo Seumen Tonou 
