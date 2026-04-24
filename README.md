# ✈️ Time Series Forecasting — Air Passenger Traffic (JFK)

## 📌 Project Overview

This project focuses on forecasting monthly passenger traffic at **JFK Airport** using time series analysis techniques.

The goal is to understand how different smoothing-based models behave and to identify the most suitable approach for real-world forecasting.

---

## 📊 Dataset

- Source: NYS Air Passenger Traffic (Kaggle)
- Scope: JFK Airport
- Frequency: Monthly
- Target: Total Passengers

---

## ⚙️ Project Structure

```
notebooks/
│
├── 01_data_understanding.ipynb
├── 02_moving_average.ipynb
├── 03_centered_moving_average.ipynb
├── 04_SES.ipynb
├── 05_holt_linear_trend.ipynb
├── 06_holt_winters.ipynb
└── 07_model_evaluation.ipynb
```

---

## 🔍 Methodology

### 1. Data Preparation

- Converted month information into datetime format
- Aggregated data at monthly level
- Created a clean time series with a unique datetime index

---

### 2. Exploratory Data Analysis

- Trend analysis
- Seasonality detection
- Rolling mean & decomposition
- Boxplots and distribution analysis

📌 Findings:

- Strong upward trend
- Clear seasonal patterns
- Increasing variance over time

---

### 3. Models Implemented

#### 🔹 Moving Average

- Basic smoothing technique
- Equal weighting across observations
- Limited forecasting capability

#### 🔹 Centered Moving Average

- Improved smoothing alignment
- Better trend visualization

#### 🔹 Simple Exponential Smoothing (SES)

- Models level only
- Uses weighted smoothing (alpha)
- ❌ Fails to capture trend and seasonality

#### 🔹 Holt’s Linear Trend

- Models level + trend
- Produces non-flat forecasts
- ❌ Cannot capture seasonality

#### 🔹 Holt-Winters (Triple Exponential Smoothing)

- Models:
  - level
  - trend
  - seasonality

- Uses multiplicative seasonality
- ✅ Best performance among all models

---

## 🧪 Model Evaluation

### 📌 Train-Test Split

Instead of random splitting, a **time-based split** is used:

- Training set → all data except last 24 months
- Test set → last 24 months

This reflects real-world forecasting scenarios.

---

### 📉 Evaluation Metrics

- MAE (Mean Absolute Error)
- RMSE (Root Mean Squared Error)

---

### 📊 Results Summary

| Model        | Performance | Notes                                 |
| ------------ | ----------- | ------------------------------------- |
| SES          | Poor        | Cannot model trend/seasonality        |
| Holt         | Medium      | Captures trend but misses seasonality |
| Holt-Winters | Best        | Captures both trend and seasonality   |

---

## 📈 Key Insights

- Time series data must be split chronologically to avoid data leakage
- Modeling only level or trend is not sufficient for seasonal data
- Incorporating seasonality significantly improves forecasting accuracy
- Holt-Winters provides the most realistic forecasts for this dataset

---

## 🚀 Conclusion

The analysis demonstrates that:

> **Holt-Winters (Triple Exponential Smoothing)** is the most suitable model for forecasting JFK passenger traffic, as it successfully captures both trend and seasonal patterns.

---

## 🛠️ Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Statsmodels
- Scikit-learn

---

## 📌 Future Improvements

- Hyperparameter tuning (alpha, beta, gamma)
- ARIMA / SARIMA models
- Deep learning approaches (LSTM)
- Model deployment

---

## 👩‍💻 Author

Merve Taşçı
