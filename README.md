# Electricity Production Forecasting using SARIMAX

## 1. Introduction
This project aims to forecast monthly electricity production using time-series modeling. Since electricity production exhibits seasonality and trends, we chose SARIMAX (Seasonal AutoRegressive Integrated Moving Average with eXogenous factors) for accurate forecasting.

## 2. Dataset Overview
The dataset consists of monthly electricity production data over a specific period.
Our goal is to build a model that can predict future electricity production based on past trends.
## 3. Exploratory Data Analysis (EDA)
### 3.1 Time-Series Visualization
A clear seasonal pattern was observed, suggesting that a seasonal model is needed.
No sudden spikes or missing values were detected, ensuring data consistency.
### 3.2 Stationarity Check: Augmented Dickey-Fuller (ADF) Test
To check stationarity, the ADF test was applied:

Null Hypothesis (H₀): The series is non-stationary (has a trend).
Alternative Hypothesis (H₁): The series is stationary.
Result: The p-value was greater than 0.05, confirming that the series was non-stationary.
### 3.3 Differencing to Achieve Stationarity
Since the data was non-stationary, seasonal differencing (D = 1) was applied.
After differencing, the ADF test confirmed that the series became stationary.
## 4. Model Selection: SARIMAX
Since the dataset exhibited seasonality, SARIMAX was chosen instead of ARIMA.

### 4.1 Auto-ARIMA for Parameter Selection
auto_arima() helped select optimal (p, d, q) and (P, D, Q, 12).
The model identified a seasonal component with a periodicity of 12 months.
4.2 SARIMAX Model Training
The final SARIMAX model was trained with:

Order = (p, d, q) → Non-seasonal ARIMA parameters.
Seasonal Order = (P, D, Q, 12) → Seasonal ARIMA parameters.
## 5. Model Evaluation
### 5.1 Forecasting Performance
The SARIMAX model successfully captured the seasonal trends in electricity production.
The predictions closely followed the actual values, validating the model’s effectiveness.
Residual analysis showed no significant autocorrelations, confirming that the model fit well.
## 6. Results & Insights
The SARIMAX model accurately modeled seasonal variations in electricity production.
The predicted values followed real-world trends, making it useful for future planning.
## 7. Conclusion & Future Enhancements
The model can be improved further by incorporating external variables like temperature, industrial demand, or economic indicators.
Alternative approaches like LSTM or Prophet could be explored for enhanced forecasting performance.
