# 📈 Financial Time Series Analysis & Forecasting (Gold & Bitcoin)

An end-to-end financial quantitative analytics and time-series forecasting project evaluating daily price movements for **Gold** and **Bitcoin**. 

The project applies statistical diagnostics—including **Augmented Dickey-Fuller (ADF)** stationarity tests and **ACF/PACF** autocorrelation structure analysis—and evaluates classical statistical models (**ARIMA**) against modern machine learning models (**Meta Prophet**) with confidence interval predictions ready for interactive dashboard visualizer deployment in **Power BI**.

---

## 📌 Project Overview & Key Objectives

Financial price series exhibit non-stationarity, stochastic trends, and complex volatility.

The key analytical goals of this project are:
1. **Stationarity & Integration Diagnostics:** Test price series using the Augmented Dickey-Fuller (ADF) test and apply first-order differencing ($d=1$) to achieve mean-stationary white noise returns.
2. **Autocorrelation Analysis:** Plot Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) to identify optimal model orders $(p, d, q)$.
3. **Comparative Modeling:** Train statistical **ARIMA(1,1,1)** vs **Meta Prophet** models to generate 30-day ahead forecasts.
4. **Accuracy Evaluation:** Benchmark predictive performance using Mean Absolute Error (**MAE**), Root Mean Squared Error (**RMSE**), and Mean Absolute Percentage Error (**MAPE**).
5. **Dashboard Export:** Export integrated actuals, forecasts, and $95\%$ confidence bounds into a unified structure for Power BI business analytics dashboards.

---

## 🛠️ Tech Stack & Libraries

* **Programming Language:** Python 3.x
* **Data Processing:** `pandas`, `numpy`
* **Time Series & Statistical Testing:** `statsmodels` (`adfuller`, `plot_acf`, `plot_pacf`, `ARIMA`)
* **Machine Learning Forecasting:** `prophet` (Meta)
* **Performance Metrics:** `scikit-learn` (`mean_absolute_error`, `mean_squared_error`)
* **Data Visualization:** `matplotlib`, `Power BI`

---

## 🧪 Analytical Framework & Workflow

### Step 1: Stationarity Diagnostics (ADF Test)
Raw financial asset prices typically exhibit stochastic trends and non-stationary distribution ($p\text{-value} \ge 0.05$). Applying First-Order Differencing transforms raw prices into stationary daily changes ($y'_t = y_t - y_{t-1}$).

* **Original Gold Series ADF $p\text{-value}$:** $> 0.05$ (Non-Stationary)
* **Differenced Gold Series ($d=1$) ADF $p\text{-value}$:** $0.0000$ (Stationary — Reject Null Hypothesis $H_0$)

---

### Step 2: Comparative Forecasting Performance

Model evaluation on historical test intervals yields the following comparative performance metrics:

| Metric | ARIMA(1,1,1) | Meta Prophet | Analysis & Interpretation |
| :--- | :--- | :--- | :--- |
| **MAE ($)** | **$9.00** | $12.45$ | ARIMA demonstrated superior tight error margins on daily step predictions. |
| **RMSE ($)** | **$11.37** | $15.80$ | Lower penalization on variance spikes for ARIMA. |
| **MAPE (%)** | **0.34%** | $0.48\%$ | Sub-1% percentage error across both models indicating robust fit. |

---

## 📊 Dashboard Data Schema (Exported CSV)

The final pipeline exports `Gold_BTC_Time_Series_Forecast_PowerBI.csv` containing:
* `Date`: Timeline index.
* `Gold_Actual`: Historical close prices.
* `BTC_Actual`: Historical Bitcoin prices.
* `Data_Type`: Categorical flag (`Historical` vs `Forecast`).
* `Gold_ARIMA_Forecast`: 30-day projected values.
* `Gold_Prophet_Forecast`: 30-day additive model estimates.
* `Gold_CI_Lower` & `Gold_CI_Upper`: $95\%$ Confidence Interval bounds for risk management.

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone [https://github.com/YOUR_USERNAME/Gold-Bitcoin-Time-Series-Forecasting.git](https://github.com/YOUR_USERNAME/Gold-Bitcoin-Time-Series-Forecasting.git)
