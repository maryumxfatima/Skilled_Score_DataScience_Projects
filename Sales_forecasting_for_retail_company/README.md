# Sales Forecasting for a Retail Store

## Project Overview
This project focuses on forecasting monthly retail sales using time series analysis. The goal is to identify patterns such as trend and seasonality in historical sales data and build a forecasting model to predict future sales. Accurate sales forecasting helps businesses improve inventory planning, marketing strategies, and financial decision-making.

The analysis was conducted using Python and statistical modeling techniques, with the final model generating a **6-month sales forecast**.

## Dataset
The dataset contains **48 months of simulated monthly retail sales data (January 2020 – December 2023).**

### Features
- **SalesAmount** – Monthly retail sales  
- **Promotion** – Binary indicator showing whether a promotion occurred  
- **HolidayMonth** – Binary indicator for holiday periods  

The dataset does not contain missing values and shows clear seasonal patterns across the years.


## Objectives
- Explore historical retail sales data  
- Identify trends and seasonal patterns  
- Perform stationarity and autocorrelation analysis  
- Build a forecasting model using **SARIMA**  
- Generate a **6-month sales forecast**
  

## Tools & Technologies
The project was implemented using the Python data science ecosystem:

- **Python**
- **Pandas**
- **NumPy**
- **Matplotlib**
- **Statsmodels**
- **Scikit-learn**

## Methodology

### Exploratory Data Analysis (EDA)
Initial analysis was performed to understand the structure and behaviour of the data. Visualizations were used to identify long-term trends and seasonal fluctuations in sales.

### Seasonal Decomposition
The time series was decomposed into three components:

- **Trend**
- **Seasonal pattern**
- **Residual noise**

This helped confirm the presence of strong annual seasonality in the dataset.

### Stationarity Testing
An **Augmented Dickey-Fuller (ADF) test** was used to evaluate stationarity. The test results indicated that the series was stationary, allowing the model to proceed without additional non-seasonal differencing.

### Model Selection
Based on **ACF and PACF analysis**, the following model was selected:

**SARIMA(1,0,1)(1,1,1)[12]**

This model captures both short-term dependencies and yearly seasonal patterns.

### Model Evaluation
The dataset was split into **training and test sets** to evaluate forecasting performance.

Evaluation metrics included:

- **MAE (Mean Absolute Error)**
- **RMSE (Root Mean Squared Error)**
- **MAPE (Mean Absolute Percentage Error)**

The model achieved a **MAPE of approximately 10%**, indicating reasonably accurate forecasts for monthly retail sales.


## Forecast Results
The trained SARIMA model was used to generate a **6-month forecast (January 2024 – June 2024).**

| Month | Forecast Sales |
|------|------|
| Jan 2024 | 16,093 |
| Feb 2024 | 13,785 |
| Mar 2024 | 13,478 |
| Apr 2024 | 11,875 |
| May 2024 | 11,385 |
| Jun 2024 | 8,810 |

The forecast reflects a **seasonal decline from the beginning of the year toward mid-year**, consistent with historical sales patterns.


## Key Insights
- Retail sales show a **consistent upward trend over time**
- There is **strong annual seasonality**, especially during holiday periods
- **Promotional months significantly increase sales**
- The SARIMA model effectively captures both **trend and seasonal behaviour**


## Future Improvements
Possible improvements to the model include:

- Using **SARIMAX** to incorporate promotion and holiday variables as external features  
- Expanding the dataset with **more years of sales data**  
- Comparing results with other forecasting models such as **Prophet or LSTM**


## Author
**Maryam Fatima**  
