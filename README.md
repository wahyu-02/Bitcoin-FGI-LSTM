# Bitcoin Price Prediction using Multivariate LSTM & Crypto Fear and Greed Index

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-orange)
![License](https://img.shields.io/badge/License-MIT-green)

## 📌 Project Overview
This project investigates the influence of the **Crypto Fear and Greed Index (FGI)** in forecasting Bitcoin prices using a **Multivariate Long Short-Term Memory (LSTM)** model. 

The high volatility of Bitcoin makes accurate prediction challenging. This study proposes integrating market sentiment (FGI) and its **monthly correlation** with price components to enhance model reliability.

**Key Findings:**
The integration of FGI and monthly correlation features significantly improved prediction accuracy, achieving a **MAPE of 2.33%**, compared to the baseline model's 6.02%.

## 📊 Features & Methodology
The project compares two LSTM models:
1.  **Model 1 (Baseline):** Uses 5 internal price features (Open, High, Low, Close, Volume).
2.  **Model 2 (Proposed):** Integrates FGI + Monthly Correlations between FGI and price components (11 features total).

**Technical Approach:**
* **Data Source:** `yfinance` (Bitcoin OHLCV) & Alternative.me API (FGI).
* **Period:** Feb 1, 2018 – May 30, 2025.
* **Preprocessing:** Sliding Window (Sequence Length tuning), MinMax Scaling.
* **Feature Engineering:** Dynamic monthly correlation between FGI and price features.
* **Hyperparameter Tuning:** Used **Hyperband** algorithm to optimize LSTM units, dropout rate, learning rate, and sequence length.

## 📈 Results
Evaluation was performed using **Mean Absolute Percentage Error (MAPE)** on the test dataset.

| Model | Features | MAPE Score | Status |
| :--- | :--- | :--- | :--- |
| **Model 1** | Historic Price Data Only | 6.02% | Baseline |
| **Model 2** | Price + FGI + Correlations | **2.33%** | **Best Performance** |

### Prediction Visualization (Model 2)
![Prediction Result](Images/prediksi_model2.png)

### Training Loss Convergence
![Loss Curve](Images/loss_model2.png)

## 🛠️ Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/USERNAME/Bitcoin-FGI-LSTM.git](https://github.com/wahyu-02/Bitcoin-FGI-LSTM.git)
