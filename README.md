
# Predicting Energy Consumption Using Machine Learning

## Project Overview

This project focuses on forecasting **hourly electricity consumption** using historical data from a transmission system operator. The dataset spans approximately **six years** and represents a **univariate time series** with strong daily, weekly, and seasonal patterns.

The goal of this assignment is to demonstrate **data understanding, feature engineering, model selection, and evaluation logic**, rather than building an enterprise-ready forecasting system.

---

## Dataset Description

* **Frequency:** Hourly
* **Duration:** ~6 years
* **Target Variable:** Electricity consumption (MWh)
* **Type:** Univariate time series

**Columns used:**

* `Start time UTC` – Timestamp
* `Electricity consumption (MWh)` – Target variable

---

## Approach

### Data Preprocessing

* Converted timestamps to datetime and set as index
* Handled missing values using time-based interpolation
* Detected and treated non-physical outliers using rolling statistics

---

### Feature Engineering

To transform the time series into a supervised learning problem, the following features were created:

* Time-based features: hour, day of week, month, weekend indicator
* Lag features: 1-hour, 24-hour, and 168-hour lags
* Rolling statistics: rolling mean and trend features

These features enable the model to learn temporal dependencies and seasonal patterns.

---

### Model Selection

The following models were trained and compared:

* Linear Regression
* Random Forest Regressor
* Gradient Boosting Regressor
* XGBoost Regressor

**XGBoost** was selected as the final model due to:

* Better handling of non-linear patterns
* Faster training and inference
* Strong ability to inherit past behavior through lag features
* Good balance between accuracy and computational efficiency

---

### Model Evaluation

Models were evaluated using:

* Mean Absolute Error (MAE)
* Root Mean Squared Error (RMSE)
* R² Score
* MAPE-based forecast accuracy

A **time-aware train–test split** was used to prevent data leakage.

---

### Interpretability & Analysis

* Actual vs Predicted plots for trend comparison
* Residual analysis to assess model bias
* Confusion matrix using binned demand levels (Low / Medium / High)
* SHAP analysis to interpret feature importance and model behavior

---

## Key Insights

* Electricity demand exhibits strong cyclical behavior
* Lag features (daily and weekly) are the most influential
* The model captures seasonality effectively
* Errors increase during sudden demand spikes due to lack of external variables

---

## Business & Sustainability Impact

Accurate energy demand forecasting supports:

* Improved grid stability
* Reduced energy wastage
* Better integration of renewable energy
* Lower carbon emissions through optimized generation planning

---

## Limitations

* Univariate dataset only
* No weather or holiday information
* Deterministic forecasts without uncertainty bounds

---

## Future Improvements

* Incorporate weather and calendar features
* Use probabilistic forecasting methods
* Apply rolling retraining strategies
* Extend to anomaly detection

---

## Conclusion

This project demonstrates a structured and practical approach to time-series forecasting using machine learning, with emphasis on **methodology, reasoning, and interpretability**, aligning with real-world data science practices.


