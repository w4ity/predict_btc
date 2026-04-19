# 📈 Bitcoin Price Trend Predictor

Welcome! This project is a **Machine Learning experiment** focused on predicting the daily price movement of Bitcoin (BTC-USD). Instead of predicting the exact price, this model focuses on a classification task: **Will the price go up or down tomorrow?**

## 🧠 Project Overview

The notebook follows a complete data science workflow:
1.  **Data Acquisition**: Pulls real-time historical data using the `yfinance` API.
2.  **Data Cleaning**: Prepares the dataset by removing irrelevant financial columns and handling missing values.
3.  **Feature Engineering**: Creates technical indicators like rolling averages and price trends across multiple time horizons (2, 5, 60, 250, and 1000 days).
4.  **Modeling**: Implements a `RandomForestClassifier` to identify patterns in market volatility.
5.  **Backtesting**: Features a custom backtesting engine to evaluate model performance across years of historical data rather than a single train/test split.

## 🛠️ Tech Stack

* **Python**
* **Pandas & Numpy**: For data manipulation.
* **Scikit-Learn**: For the Random Forest Machine Learning model.
* **yfinance**: For financial market data.
* **Matplotlib**: For visualizing price history and trends.

## 🚀 How to Run

1.  **Install dependencies**:
    ```bash
    pip install yfinance pandas scikit-learn matplotlib
    ```
2.  **Open the Notebook**:
    Launch `jupyter notebook` and open `predict_btc.ipynb`.
3.  **Run All Cells**:
    The script will fetch the latest BTC data and train the model automatically.

## 📊 Logic Behind the Model

The model uses a "Target" variable defined as:
$$Target_i = \begin{cases} 1 & \text{if } Close_{i+1} > Close_i \\ 0 & \text{otherwise} \end{cases}$$

By calculating rolling averages, the model attempts to capture market momentum and distinguish "signal" from "noise".
