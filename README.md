# Weather-Analysis
# Project Overview
This project performs time series analysis and forecasting of daily weather data for the United States.
We compare statistical modeling (SARIMA) with machine learning approaches (XGBoost) to predict future daily temperatures.

The workflow includes:

- Data cleaning & preprocessing
- Exploratory Data Analysis (EDA)
- Outlier detection
- Stationarity testing
- Forecasting with SARIMA & XGBoost
- Performance evaluation

# Dataset
Source: https://www.kaggle.com/datasets/nelgiriyewithana/global-weather-repository/code


# Data Preprocessing
- Convert timestamps to datetime objects
- Filter for the United States
- Drop unnecessary columns (moon/sun data, redundant fields, detailed air quality breakdown)
- Resample to daily mean values
- Keep only numeric variables for correlation and modeling

# Exploratory Data Analysis
- Correlation hearmap
- Pairplot
- Monthly temperature boxplot to detect seasonality
- Time series plots to identify trends and anomalies

# Outlier Detection
- Visualized with boxplots and time series plots
- Used rolling median and Median Absolute Deviation to detect anomalies in temperature

# Stationarity Testing
- Applied Augmented Dickey-Fuller (ADF) Test
- Differenced the series if p-value > 0.05 (non-stationary)

# Forecasting Models
- SARIMA performance: RMSE = 0.437 ; MAE = 0.326
- XGBoost (Univariate): RMSE= 0.636 ; MAE: 0.452
- XGBoost (Multivariate): RMSE = 4.164 ; MAE = 2.960

| Model                  | RMSE      | MAE       | Notes                                     |
| ---------------------- | --------- | --------- | ----------------------------------------- |
| SARIMA                 | **0.437** | **0.326** | Best performer, captured seasonality well |
| XGBoost (Univariate)   | 0.636     | 0.452     | Decent but less accurate                  |
| XGBoost (Multivariate) | 4.164     | 2.960     | Poor, likely overfit due to small dataset |

# Possible Improvements
- Use hourly data for models like XGBoost to
- Try advanced models like Prophet or LSTM neural networks

