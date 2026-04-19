# 📈 Bitcoin Price Trend Predictor

Welcome! This project is a **Machine Learning experiment** focused on predicting the daily price movement of Bitcoin (BTC-USD). Instead of predicting the exact price, this model focuses on a classification task: **Will the price go up or down tomorrow?**

---

## 🧠 Project Overview

The notebook follows a complete data science workflow:
1.  **Data Acquisition**: Pulls historical data for "BTC-USD" using the `yfinance` API.
2.  **Data Cleaning**: Prepares the dataset by removing irrelevant columns like `Dividends` and `Stock Splits`.
3.  **Feature Engineering**: Creates technical indicators like rolling averages and price trends across multiple time horizons: 2, 5, 60, 250, and 1000 days.
4.  **Modeling**: Implements a `RandomForestClassifier` with `n_estimators=100` and `min_samples_split=100` to identify patterns while avoiding overfitting.
5.  **Backtesting**: Features a custom `backtest` function to evaluate model performance across years of historical data rather than a single split.

---

## 📊 Model Logic & Strategy

> [!TIP]
> ### 🔍 Mathematical Approach
> The core objective is to predict if the Bitcoin price will increase the following day. We define a binary **Target** variable based on the closing price:
>
> $$Target_i = \begin{cases} 1 & \text{if } Close_{i+1} > Close_i \\ 0 & \text{otherwise} \end{cases}$$
>
> * **1 (Bullish)**: The price goes up tomorrow. The model identifies this as a potential Buy/Hold signal.
> * **0 (Bearish)**: The price goes down or stays the same. The model identifies this as a Sell/Avoid signal.
>
> By calculating rolling averages, the model attempts to capture market momentum and distinguish "signal" from "noise".

---

## 🛠️ Tech Stack

* **Python**: Core programming language.
* **Pandas & Numpy**: For data manipulation and cleanup.
* **Scikit-Learn**: Specifically for the `RandomForestClassifier` and `precision_score` metrics.
* **yfinance**: For fetching real-time financial market data.
* **Matplotlib**: For visualizing price history and model trends.

---

## 🚀 How to Run

1.  **Install dependencies**:
    ```bash
    pip install yfinance pandas scikit-learn matplotlib
    ```
2.  **Open the Notebook**:
    Launch `jupyter notebook` and open `predict_btc.ipynb`.
3.  **Run All Cells**:
    The script will fetch the latest BTC data and train the model automatically.
