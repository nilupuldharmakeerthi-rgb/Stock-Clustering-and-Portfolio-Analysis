# Stock-Clustering-and-Portfolio-Analysis
This project applies unsupervised machine learning to construct and evaluate portfolios from 100 U.S. equities. Traditional K-Means clustering is compared with Deep Clustering across single‑, two‑, and multi‑feature setups. The resulting clusters are used to build optimized portfolios and benchmark performance.
Workflow
1) Data Collection — 2 years of daily closing prices for 100 stocks pulled via yfinance, with outlier removal.
2) xploratory Analysis — Price classification (Very Low → Top) and volatility profiling (weekly/monthly/quarterly) across price tiers.
Clustering Experiments
          Single-feature: Monthly Volatility
          Two-feature: Average Price vs. Monthly Volatility, and Annual Return vs. Annual Volatility
          Multi-feature: 10 financial indicators (return, volatility, Sharpe ratio, skewness, kurtosis, max drawdown, momentum, etc.) reduced via PCA
          Each experiment compares K-Means vs. Deep Clustering using Silhouette Scores
Portfolio Construction
Top stocks selected from each cluster by Sharpe Ratio
Portfolios optimized for Maximum Sharpe Ratio (MSR), Global Minimum Variance (GMV), and Utility Maximization (risk aversion A = 1, 3, 5)
Benchmarking — Portfolio performance compared against the S&P 500 (^GSPC) and against an optimized portfolio built from the full 100-stock universe.
## Authors
Group 04 — FM 4054 Agent-Based Modeling
University of Colombo
