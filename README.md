# ✈️ Time Series Forecasting: SARIMA vs Prophet

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/image1.png" width="500">
</p>

This repository presents a comparative time series forecasting study using two prominent models: **Seasonal ARIMA (SARIMA)** and **Prophet**. The analysis focuses on modeling monthly international airline passenger volumes, aiming to assess each model’s forecasting performance, interpretability, and suitability for real-world business applications.

- 📘 [`ForecastingPassengers.ipynb`](https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/ForecastingPassengers.ipynb)  
  A comprehensive notebook outlining the exploratory analysis, feature engineering, model development, and performance evaluation.

- 📖 [Read the full article on Medium](https://medium.com/@alalparkh/time-series-forecasting-sarima-vs-prophet-e957931a2aff)  
An in-depth explanation of the steps taken, insights gained, and model comparisons.
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
- 🔍 Seasonal decomposition to isolate trend, seasonality, and residual components  
- 🔄 Logarithmic transformation and differencing applied to stabilize variance and normalize the distribution  
- 🧪 Stationarity assessment via the Augmented Dickey-Fuller (ADF) test  
- 🔁 Autocorrelation (ACF) and partial autocorrelation (PACF) analysis to guide SARIMA configuration

---

## ⚙️ Forecasting Methodologies

### 🔹 SARIMA (Seasonal ARIMA)

- Applied AIC-based grid search to optimize seasonal and non-seasonal hyperparameters  
- Trained on a log-transformed series to stabilize variance  
- Effectively captured multiplicative seasonality and trend  
- Residuals analyzed to assess model assumptions and forecasting reliability  
- Evaluated using key metrics: **MAPE**, **RMSE**, and **MAE**


### 🔸 Facebook Prophet

- Configured with a **multiplicative seasonal model** and **95% confidence interval**  
- Backtested using **cross-validation** with a rolling forecast horizon of 12 months  
- Optimized with grid search on key parameters: `changepoint_prior_scale` and `seasonality_prior_scale`  
- Evaluated using key metrics: **MAPE**, **RMSE**, and **MAE**



---
## 📈 Model Evaluation & Comparison

The SARIMA model effectively captured the underlying temporal patterns, particularly within the one-year forecast horizon. Although it showed a slight tendency to overestimate peak values, its forecasts remained closely aligned with the actual data.

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/sarima_predicted.png" width="600">
</p>

The Prophet model demonstrated strong short-term accuracy with well-calibrated uncertainty intervals. While the intervals naturally widen over time, they narrowed toward the end of the forecast window—potentially indicating greater reliability for mid-range forecasts.

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/Prophet_Forecast.png" width="600">
</p>

Both models were evaluated on a held-out test set using standard regression metrics:

| Metric   | SARIMA   | Prophet  |
|----------|----------|----------|
| **MAE**  | 927.14   | **885.42** |
| **RMSE** | 1,196.16 | **1,023.27** |
| **MAPE** | 4.68%    | **4.54%**  |

Prophet outperformed SARIMA across all evaluation metrics, delivering more accurate and consistent forecasts for this dataset. Its performance and ease of tuning made it a better fit for the forecasting objective at hand.

<p align="center">
  <img src="https://github.com/aliaksparkh/Time-Series-Forecasting/blob/main/SARIMA_vs_Prophet_.png" width="600">
</p>

## 🧠 Conclusion

- **SARIMA** remains a reliable and interpretable model, particularly effective when seasonality patterns are well-defined and consistent.
- **Prophet** offers a highly practical solution with minimal configuration, making it ideal for fast, business-oriented forecasting where flexibility and responsiveness are key.
- While SARIMA provides more control and statistical depth, Prophet stands out for its adaptability, performance, and ease of deployment in real-world environments.


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

