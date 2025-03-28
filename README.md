# Electricity Demand Forecasting using ARIMA and SARIMA Models

## Project Overview
This project applies ARIMA (AutoRegressive Integrated Moving Average) and SARIMA (Seasonal ARIMA) models to analyze and forecast electricity sales trends in the United States. Using monthly electricity consumption data from 2010 to 2023, the study captures long-term trends and seasonal patterns in power usage across different economic sectors.

By leveraging time series modeling techniques, this analysis provides data-driven insights for energy policymakers, utility companies, and researchers interested in demand forecasting.

## Dataset
- Source: U.S. Energy Information Administration (EIA) - Monthly Form EIA-861M
- Time Frame: January 2010 – December 2023 (168 monthly observations)
- Key Variable: Sales_total (aggregated electricity consumption across residential, commercial, industrial, and transportation sectors)
- Other Features: Revenue, customer counts, and sector-specific sales data

## Data Preprocessing
- Combined Year and Month into a datetime index
- Removed commas and converted variables to numeric format
- Conducted Augmented Dickey-Fuller (ADF) test for stationarity
- Applied first-order differencing for stabilization

## ARIMA Model
Why ARIMA?
- Suitable for non-seasonal time series data with trends
- Combines autoregression (AR), differencing (I), and moving average (MA)

Pros:
- Flexible and adaptable to various datasets
- Accurate for non-seasonal trends
- Simple to implement in Python

Cons:
- Requires stationary data
- Cannot capture seasonal patterns
- Parameter selection can be complex

Model Steps:
- Conducted ADF test
- Used ACF and PACF plots to estimate parameters
- Applied Auto-ARIMA and selected ARIMA(2,0,2)
- Forecasted next 36 months and re-integrated differenced values

## SARIMA Model
SARIMA extends ARIMA to handle seasonality by adding seasonal components:
SARIMA(p, d, q) × (P, D, Q, s), where s=12 for monthly data

Model Steps:
- Used seasonal decomposition to visualize components
- Auto-SARIMA selected SARIMA(1,0,2)x(2,1,2,12)
- Residuals and confidence intervals validated model fit
- Forecasted next 36 months of seasonal energy demand

## Results
- ARIMA effectively captured long-term trends
- SARIMA improved accuracy by modeling seasonal variations
- Both models support planning for future energy consumption

## Files Included
- ARIMA_Updated.ipynb – Jupyter Notebook with full analysis
- Elec_sales.xlsx – Raw dataset


