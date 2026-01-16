# Dhrumal_Patel_Predective_analytics
# Energy Consumption Forecasting (Hourly Time Series)

This project predicts **hourly electricity consumption (MWh)** using 6 years of historical data from a transmission system operator.

## Dataset
The dataset contains:
- `Start time UTC`
- `End time UTC`
- `Electricity consumption (MWh)`

## Approach
This is a **time-series forecasting** problem, so the model learns patterns from past values.

### Preprocessing
- Converted timestamps to `datetime` and sorted by time
- Ensured continuous hourly frequency using `asfreq("h")`
- Filled missing values using time-based interpolation
- Clipped extreme outliers to avoid unstable training

### Feature Engineering (Main Focus)
Created features to capture seasonality and dependency:
- Time features: `hour`, `weekday`, `month`, `is_weekend`
- Lag features: `lag_1`, `lag_24`, `lag_168`
- Rolling feature: `roll_mean_24`

## Model
Used **RandomForestRegressor** because it is simple, easy to understand, and performs well with engineered lag/rolling features.

## Evaluation Metrics
- **MAE** (Mean Absolute Error)
- **RMSE** (Root Mean Squared Error)

## Output
The notebook prints:
- MAE, RMSE
- Sample predictions
- Feature importance ranking
- Actual vs Predicted plot

## How to Run
1. Open the notebook in Kaggle / Jupyter
2. Update the dataset path if needed
3. Run all cells
