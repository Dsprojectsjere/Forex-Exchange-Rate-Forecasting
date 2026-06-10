# 💱 Forex Exchange Rate Forecasting

**Jeremiah Kabeya | BSc Data Science, University of Hertfordshire** 🎓

---

## 📌 Introduction

This project explores forecasting foreign exchange rates using multiple machine learning and statistical approaches. The dataset used is the **Federal Reserve Foreign Exchange Rates** dataset, covering daily exchange rates across multiple currency pairs.

The goal is to compare how different modelling paradigms — classical time-series statistics vs. gradient-boosted machine learning — handle the challenge of predicting currency prices. Each notebook is a standalone experiment with a different model, building toward a comprehensive comparative study.

> ⚠️ **Work in Progress** — a third model is currently in development.

---

## 📂 Notebooks

| Notebook | Model | Target Currency |
|----------|-------|-----------------|
| `Forex_Using_ARIMA.ipynb` | ARIMA (Auto) | EUR/USD |
| `Forex_Using_XgBoost.ipynb` | XGBoost + Bayesian Optimisation | GBP/USD |
| *Coming soon* | *TBD* | *TBD* |

---

## 📈 Notebook 1 — ARIMA (`Forex_Using_ARIMA.ipynb`)

A classical statistical approach to time-series forecasting on the **EUR/USD** exchange rate.

**Pipeline:**
- 🔧 Data cleaning — removed non-numeric `ND` values, forward-filled missing dates, resampled to weekly frequency
- 🔍 EDA — plotted daily, weekly, monthly, and yearly trends; distribution plots and seasonal decomposition
- 📉 Stationarity testing — Augmented Dickey-Fuller (ADF) test with ACF/PACF analysis
- 🤖 Model selection — `auto_arima` with AIC-based order selection and seasonality detection
- 🧪 Train/test split — 80/20 time-based split with walk-forward validation
- 📊 Evaluation — R², MAE, RMSE, MAPE

**🛠️ Libraries:** `statsmodels`, `pmdarima`, `pandas`, `matplotlib`, `seaborn`, `scikit-learn`

---

## 📈 Notebook 2 — XGBoost (`Forex_Using_XgBoost.ipynb`)

A machine learning approach to the same forecasting problem, applied to the **GBP/USD** exchange rate.

**Pipeline:**
- 🔧 Data cleaning — same preprocessing as ARIMA (date parsing, NA handling, forward fill)
- 🏗️ Feature engineering — lag features (1-day, 7-day, 30-day), rolling means (7/30/90-day windows), rolling standard deviations, time-based features (year, month, day of week, day of year)
- ✂️ Time-based train/test split — last 30 days held out as test set
- ⚙️ Hyperparameter tuning — Bayesian Optimisation over `max_depth`, `gamma`, `colsample_bytree` with 3-fold cross-validation
- 📊 Evaluation — MAE, MSE, RMSE, MAPE, R²

**🛠️ Libraries:** `xgboost`, `bayesian-optimization`, `pandas`, `plotly`, `scikit-learn`, `numpy`

---

## 💡 What This Project Demonstrates

- 🔁 **Model comparison mindset** — applying two fundamentally different approaches to the same problem to understand the trade-offs between interpretability and predictive power
- 📐 **Rigorous time-series methodology** — stationarity testing, walk-forward validation, and avoiding data leakage in temporal splits
- 🏗️ **Feature engineering for ML on time-series** — constructing lag and rolling window features to give XGBoost the temporal context it doesn't natively understand
- ⚙️ **Automated tuning** — Bayesian Optimisation over XGBoost hyperparameters rather than brute-force grid search
- 📊 **Consistent evaluation** — using the same suite of metrics (MAE, RMSE, MAPE, R²) across models to make fair comparisons

---

## ⚙️ Tech Stack

`Python` · `XGBoost` · `ARIMA` · `pmdarima` · `statsmodels` · `Bayesian Optimisation` · `Pandas` · `NumPy` · `Matplotlib` · `Seaborn` · `Plotly` · `Scikit-Learn` · `Jupyter Notebook`

---

## 🗂️ Dataset

**Federal Reserve Foreign Exchange Rates**
Daily exchange rates for multiple currency pairs against the USD. Sourced as `Foreign_Exchange_Rates.xls`.


