# Apparent-Temperature-Prediction-using-Regression-Models

## Overview

This project focuses on predicting **Apparent Temperature (°C)** using environmental features like temperature, humidity, wind speed, and pressure. It is a continuation of a prior assignment where only **humidity** was used with **Linear Regression**, but the results were not satisfactory. In this extended version, multiple features and advanced models were used to improve performance.

- **MAE (Mean Absolute Error):** 0.57  
- **MSE (Mean Squared Error):** 0.76  
- **Best Model:** Random Forest Regressor

## Dataset

The dataset used in this project is from [Kaggle - Szeged Weather Dataset](https://www.kaggle.com/datasets/budincsevity/szeged-weather?resource=download). It contains weather-related features recorded in Szeged, Hungary.

### Features:
- `Temperature (C)`
- `Humidity`
- `Wind Speed (km/h)`
- `Pressure (millibars)`
- `Summary` (weather condition, categorical)

### Target:
- `Apparent Temperature (C)`

---

## Project Workflow

### 1. Preprocessing & Feature Engineering

- **One-Hot Encoding** of the categorical `Summary` column
- **Standardization** using `StandardScaler` for numerical features
- **Feature Engineering**:
  - `temp_humidity_ratio` = Temperature / Humidity
  - `wind_pressure_score` = Wind Speed * Pressure

### 2. Dimensionality Reduction

- Applied **PCA (Principal Component Analysis)** to visualize variance distribution.
- PCA did not significantly reduce dimensionality but was useful for understanding correlations.

### 3. Model Building

Models implemented:
- Linear Regression (Baseline)
- Random Forest Regressor (Best performing)

Other models, such as Ridge, Lasso, and Gradient Boosting, were considered but not implemented due to Random Forest's strong performance.

### 4. Hyperparameter Tuning

Used `GridSearchCV` with 5-fold cross-validation to tune `RandomForestRegressor`.  
Hyperparameters tuned:
- `n_estimators`: [100, 200]
- `max_depth`: [5, None]

---

## Results

| Metric | Score |
|--------|-------|
| R² Score | 0.993 |
| MAE      | 0.571  |
| MSE      | 0.763  |

- Residuals were minimal and randomly distributed.
- No overfitting was observed between training and test data.

---

## Visualizations

- Histograms for feature distributions  
- Heatmaps for feature correlation  
- Residual plots for error analysis  

All visualizations confirmed strong model performance and stable error patterns.

---

## Conclusion

This project significantly improved upon the initial single-feature model by integrating multiple relevant features and a well-tuned ensemble model. With **MAE = 0.57** and **MSE = 0.76**, the **Random Forest Regressor** delivered reliable and accurate results. The model can potentially be deployed for real-time weather monitoring or integrated with IoT sensor systems.

