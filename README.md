# PEC---Predicting-Energy-Consumption
🔋 Predicting Energy Consumption Using Machine Learning
📌 Project Overview

This project focuses on forecasting hourly electricity consumption using historical data from a transmission system operator.
The dataset spans approximately six years and represents a univariate time series with strong daily, weekly, and seasonal patterns.

The objective of this work is not enterprise-level deployment, but to demonstrate:

Understanding of time-series data

Feature engineering for machine learning

Model selection and evaluation

Clear reasoning and interpretability

📂 Dataset Description

Frequency: Hourly

Duration: ~6 years

Target Variable: Electricity consumption (MWh)

Type: Univariate time series

Columns used:

Start time UTC – timestamp (hourly)

Electricity consumption (MWh) – target variable

⚙️ Approach Summary
1. Data Preprocessing

Converted timestamps to datetime and set as index

Checked for missing values and applied time-based interpolation

Detected outliers using rolling statistics and treated non-physical anomalies

2. Feature Engineering

To convert the time series into a supervised learning problem:

Time-based features: hour, day of week, month, weekend indicator

Lag features: previous 1 hour, 24 hours, and 168 hours

Rolling statistics: rolling mean and trend features

These features help the model learn temporal dependencies and seasonal patterns.

3. Model Selection

Multiple regression models were trained and compared:

Linear Regression (baseline)

Random Forest

Gradient Boosting

XGBoost

XGBoost was selected as the final model due to:

Better handling of non-linear patterns

Faster training compared to traditional boosting

Strong ability to inherit past behavior via lag features

Good balance between accuracy and computational efficiency

4. Model Evaluation

The models were evaluated using:

MAE (Mean Absolute Error) – primary metric (interpretable in MWh)

RMSE (Root Mean Squared Error)

R² score

MAPE-based forecast accuracy

A time-aware train–test split was used to avoid data leakage.

5. Interpretability & Analysis

Actual vs Predicted plots to assess trend learning

Residual analysis to detect bias

Confusion matrix (binned Low/Medium/High demand) for decision-level insight

SHAP analysis to interpret feature importance and model behavior

📊 Key Insights

Electricity demand is highly cyclical and habit-driven

Lag features (daily and weekly) are the most influential

The model captures seasonality effectively but struggles during sudden demand spikes (expected without weather data)

🌱 Business & Sustainability Impact

Accurate energy consumption forecasting can:

Improve grid stability

Reduce energy overproduction

Support renewable energy integration

Lower carbon emissions through better planning
