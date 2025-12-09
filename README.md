Kaggle dataset link - https://www.kaggle.com/datasets/rakannimer/air-passengers
📊 Airline Passengers Time-Series Analysis

This project performs a complete exploratory and statistical analysis of the classic Airline Passengers dataset.
The goal is to understand the structure of the time series, identify trend and seasonality patterns, check stationarity, and determine whether the series behaves additively or multiplicatively.

🚀 Project Overview

This analysis explores:

Time-series visualization

Rolling statistics (mean, variance, standard deviation)

Autocorrelation behavior

Additive and multiplicative seasonal decomposition

Trend growth estimation

Stationarity testing using the Augmented Dickey–Fuller (ADF) test

Variance–mean relationships to identify multiplicative seasonality

The notebook identifies the nature of the time series and provides insights crucial for modeling and forecasting.

📁 Dataset

The dataset contains monthly totals of international airline passengers.
Columns:

Month – time index

Passengers – number of passengers (in thousands)

A 12-month seasonal cycle is assumed.

🔍 Key Steps in the Analysis
1. Data Loading & Preprocessing

Load CSV using pandas.

Convert the Month column into the DataFrame index.

Inspect dataset structure, shape, and data types.

2. Exploratory Visualizations

Line plot of the passenger series

Rolling mean and rolling variance

Histogram & Q-Q Plot (distribution analysis)

Boxplot for outlier inspection

Autocorrelation plot (ACF) showing strong annual seasonality

3. Trend Growth Rate

A linear regression on the trend component estimates the annual growth rate, confirming a strong upward trend in air travel demand.

4. Stationarity Testing

Using the ADF test, we found:

Original series → Non-stationary

Trend component → Non-stationary

Residuals → Stationary

This indicates that the data contains trend and seasonality but becomes stationary once those components are removed.

5. Seasonal Decomposition

Both additive and multiplicative decompositions were performed.

Findings:

Additive model: Seasonal amplitude constant

Multiplicative model: Seasonal amplitude increases with series level

Multiplicative decomposition produced lower residual variance, indicating a better fit

6. Variance–Mean Relationship

Rolling windows showed that:

Variance increases as the mean increases

Strong positive correlation between mean and variance

This is a defining feature of multiplicative time-series behavior.

🧠 Key Insights & Learnings

The airline passenger time series is non-stationary.

It exhibits a clear upward trend (increasing demand).

Seasonality is strong and annual.

The series is fundamentally multiplicative, not additive.

Residuals after decomposition are stationary, meaning:

They are suitable for statistical modeling (e.g., ARIMA).

Multiplicative models like Holt-Winters Exponential Smoothing or SARIMA with log-transform are appropriate for forecasting.
