# Sardinia Electricity Load Forecasting (2020-2024)

## Project Overview
This project analyzes and forecasts electricity load in Sardinia from 2020 to 2024. The goal is to understand load patterns, evaluate forecast accuracy, and build a predictive model using machine learning techniques.

**Key objectives:**
- Analyze historical electricity load and forecast data.
- Explore patterns by time, season, and weather.
- Engineer relevant features for machine learning.
- Build a LightGBM model to predict electricity load.
- Evaluate model performance with MAE, RMSE, and MAPE.

## Dataset
The dataset contains electricity load and forecast values, along with weather data and time features.

**Columns:**
- `total_load`: Actual electricity load (MW)
- `forecast_load`: Forecasted electricity load (MW)
- `Year, Month, Day, Weekday, Hour, Minute`: Date and time features
- `Season`: Season encoded (0: Winter, 1: Spring, 2: Summer, 3: Autumn)
- Weather features: `temperature`, `dew_point`, `humidity`, `precipitation`, `wind_direction`, `wind_speed`, `wind_gust`, `pressure`, `sunshine`, `weather_code`
- Lag features: `load_lag1`, `load_lag2`, `load_lag3`
- `prediction`: Predicted load by the model

**Data Source:** Historical electricity load and weather data for Sardinia (2020–2024).

## Exploratory Data Analysis (EDA)
- **Load patterns:** Daily, weekly, and seasonal trends identified.
- **Heatmaps:** Hour vs weekday average load.
- **Error analysis:** Forecast errors examined across time and season.
- **Weather analysis:** Temperature, precipitation, and wind impact on load.

## Feature Engineering
- Created lag features (`load_lag1`, `load_lag2`, `load_lag3`) for time-series modeling.
- Encoded `Season` as integers for model input.
- Combined electricity load data with weather features for improved prediction accuracy.

## Modeling
**Model used:** LightGBM Regressor

**Training setup:**
- 80% training, 20% testing split
- Features: Time, weather, lagged load values, season
- Target: `total_load`

**Performance Metrics:**
- MAE: 11.19 MW
- RMSE: 15.97 MW
- MAPE: 1.14%

## Visualizations
- Predicted vs Actual load
- Feature importance
- Error distribution by hour, weekday, and season

## Key Insights
- Electricity load shows strong daily and seasonal patterns.
- Weather features significantly improve forecast accuracy.
- Lag features help the model capture short-term dependencies.
- LightGBM provides accurate predictions with low error metrics.
