# ✈️ Time Series Forecasting: SARIMA vs Prophet

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/image1.png" width="500">
</p>

This repository presents a comparative time series forecasting study using two prominent models: **Seasonal ARIMA (SARIMA)** and **Facebook Prophet**. The analysis focuses on modeling monthly international airline passenger volumes, aiming to assess each model’s forecasting performance, interpretability, and suitability for real-world business applications.

- 📘 [`ForecastingPassengers.ipynb`](https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/ForecastingPassengers.ipynb)  
  A comprehensive notebook outlining the exploratory analysis, feature engineering, model development, and performance evaluation.

---

## 📊 Dataset Overview

The dataset captures the **monthly number of international airline passengers** between **January 2008 and December 2019**. It is a modernized adaptation of the classic [AirPassengers dataset](https://stat.ethz.ch/R-manual/R-devel/library/datasets/html/AirPassengers.html), updated to reflect contemporary travel patterns and serve as a benchmark for forecasting accuracy.

- Format: `CSV`  
- Frequency: Monthly  
- Source: [Airline customers.csv](https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/Airline%20customers.csv)

---

## 🔍 Exploratory Data Analysis (EDA)

To uncover underlying patterns and inform model selection, the following analytical steps were undertaken:

- 📈 Visual inspection of long-term trends, seasonal fluctuations, and distributional shifts  
- 🧪 Stationarity assessment via the Augmented Dickey-Fuller (ADF) test  
- 🔍 Seasonal decomposition to isolate trend, seasonality, and residual components  
- 🔄 Logarithmic transformation and differencing for variance stabilization  
- 🔁 Autocorrelation (ACF) and partial autocorrelation (PACF) analysis to guide SARIMA configuration

---

## ⚙️ Forecasting Methodologies

### 🔹 SARIMA (Seasonal ARIMA)

- Leveraged `pmdarima.auto_arima` with AIC-based grid search to optimize seasonal and non-seasonal hyperparameters  
- Trained on log-transformed, differenced series to ensure stationarity  
- Captures multiplicative seasonality and autocorrelation dynamics with high precision

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/sarima1.png" width="600">
</p>

---

### 🔸 Facebook Prophet

- Implemented with a **multiplicative seasonal model** and **95% confidence interval**  
- Conducted backtesting through **cross-validation** with a rolling forecast horizon of 12 months  
- Intuitive handling of trend changes and anomaly robustness

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/prophet1.png" width="600">
</p>

---

## 📈 Model Evaluation & Comparison

Performance was benchmarked using common regression metrics on a held-out test set:

| Metric | SARIMA | Prophet |
|--------|--------|---------|
| **MAE** | 1,644.53 | 1,303.10 |
| **RMSE** | 1,789.49 | 1,529.70 |
| **MAPE** | 8.49% | 6.54% |

Prophet demonstrated superior performance across all evaluated metrics, particularly excelling in capturing trend shifts and nonlinear seasonal effects.

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/sarima%20vs%20prophet.png" width="600">
</p>

---

## 🧠 Conclusion

- **SARIMA** remains a robust and interpretable model, particularly effective when seasonality is known and stable.
- **Prophet** offers a compelling alternative for practitioners, providing flexibility, minimal tuning, and strong out-of-the-box performance in volatile business environments.
- While SARIMA is advantageous in terms of statistical rigor, Prophet's practicality and predictive strength make it the preferred choice for rapid deployment and operational forecasting.

---

## 🚀 How to Run This Project

#### 1. Clone the repo:

   ```bash
   git clone https://github.com/yourusername/Time-Series-Forecasting.git
   cd Time-Series-Forecasting
```
#### 2. Install requirements:
   ```bash
   pip install -r requirements.txt
```
#### 3.  Launch the notebook:
   ```bash
   jupyter notebook ForecastingPassengers.ipynb
```

---

## 📜 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). You are free to use, modify, and distribute this project with proper attribution.

