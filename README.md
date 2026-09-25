# Stock-Clustering-and-Portfolio-Analysis

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/nilupuldharmakeerthi-rgb/Stock-Clustering-and-Portfolio-Analysis/blob/main/Group%201_Stock%20Clustering%20and%20Portfolio%20Analysis.ipynb)

**Course:** FM 3056 — Group Assignment

**Group Members:**
- T.R.S.K. Fernando
- M.D.K.N. Dharmakeerthi

## Overview

This project applies unsupervised machine learning to build and evaluate investment portfolios from a universe of 100 actively traded U.S. equities. We compare traditional **K-Means clustering** against **Deep Clustering (autoencoder + K-Means)** across single-feature, two-feature, and multi-feature setups, then use the resulting clusters to construct and benchmark optimized portfolios.

## Workflow

1. **Data Collection** — 2 years of daily closing prices for 100 stocks pulled via `yfinance`, with outlier removal.
2. **Exploratory Analysis** — Price classification (Very Low → Top) and volatility profiling (weekly/monthly/quarterly) across price tiers.
3. **Clustering Experiments**
   - Single-feature: Monthly Volatility
   - Two-feature: Average Price vs. Monthly Volatility, and Annual Return vs. Annual Volatility
   - Multi-feature: 10 financial indicators (return, volatility, Sharpe ratio, skewness, kurtosis, max drawdown, momentum, etc.) reduced via PCA
   - Each experiment compares K-Means vs. Deep Clustering using Silhouette Scores
4. **Portfolio Construction**
   - Top stocks selected from each cluster by Sharpe Ratio
   - Portfolios optimized for Maximum Sharpe Ratio (MSR), Global Minimum Variance (GMV), and Utility Maximization (risk aversion A = 1, 3, 5)
5. **Benchmarking** — Portfolio performance compared against the S&P 500 (^GSPC) and against an optimized portfolio built from the full 100-stock universe.

## Key Finding

The cluster-based 6-stock portfolio (selected via Deep Clustering) performs competitively against the full 100-stock universe, offering a strong risk-return trade-off with significantly lower management complexity.

## Tech Stack

- **Data:** `yfinance`
- **Analysis:** `pandas`, `numpy`, `scipy`
- **Machine Learning:** `scikit-learn` (K-Means, PCA, StandardScaler), `tensorflow`/`keras` (autoencoder)
- **Optimization:** `scipy.optimize`
- **Visualization:** `matplotlib`, `seaborn`

## Repository Contents

| File | Description |
|---|---|
| `Group 1_Stock Clustering and Portfolio Analysis.ipynb` | Full analysis notebook — data collection, clustering experiments, portfolio construction, and benchmarking |

## How to Run

```bash
pip install yfinance pandas numpy scipy scikit-learn tensorflow matplotlib seaborn
jupyter notebook "Group 1_Stock Clustering and Portfolio Analysis.ipynb"
```

Or click the **Open in Colab** badge above to run it directly in your browser, no setup needed.
