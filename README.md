# black-litterman_and_more
# Black-Litterman Portfolio Optimization with Rolling Return and Risk Analysis

This project implements **Black-Litterman portfolio optimization** alongside classical models (Market Cap, Mean-Variance Optimization, Maximum Sharpe Ratio) to construct and evaluate equity portfolios. The analysis is conducted in Python with a focus on **daily excess returns**, **custom views**, and **rolling performance metrics**.

---

## Project Objectives

- Model expected returns using the Black-Litterman framework
- Integrate investor views on specific assets and asset groups
- Compare portfolio allocations across different **risk aversion profiles**
- Evaluate performance using:
  - Annual return, volatility, and Sharpe ratio
  - Daily Value-at-Risk (VaR) and Max Drawdown
  - Rolling performance metrics (return, volatility, Sharpe)
- Visualize **cumulative returns** and **drawdowns** over time

---
## Data Acquisition and Asset Selection

- **Data Source**: All historical returns and volumes data is fetched from Yahoo Finance.
- **Asset Universe**: The portfolio initially considers a broad set of equities and ETFs across sectors and asset classes.
- **Filtering Step**:
  - Pairwise correlations of daily returns are computed.
  - Highly correlated assets (above a defined threshold) are filtered to reduce redundancy and ensure better diversification.
    
## Covariance Matrix Estimation with Ledoit-Wolf Shrinkage

Accurate estimation of the asset return covariance matrix is essential for portfolio optimization. In this project, we apply the **Ledoit-Wolf shrinkage estimator** to reduce noise and improve stability in the covariance matrix used in Black-Litterman and MVO calculations.

## Models Implemented

1. **Market Cap Weighted Portfolio**  
2. **Mean-Variance Optimization (MVO)**  
3. **Maximum Sharpe Ratio (MSR)**  
4. **Black-Litterman Model (BL)** with customized views (examples below):
   - NVDA expected to outperform TSLA by 3% annually
   - BLDR expected to return 60% annually
   - IAU expected to outperform TLT by 2% annually
   - Growth assets expected to outperform defensives by 5%

Each model's weights are computed and applied to historical daily returns.

---

## Risk Aversion Scenarios

The Black-Litterman model is further tested across three investor profiles:

- **Risk Seeking**
- **Risk Neutral** *(market average)*
- **Risk Averse**

Comparative analysis of resulting allocations and performance provides insight into how investor preferences shape portfolio construction.

---

## Visualizations

- **Daily Cumulative Returns** for all models
- **Maximum Drawdown over Time**
- **Rolling 60-day Metrics**:
  - Return
  - Volatility
  - Sharpe Ratio  
  *(with zoom functionality by date window)*
