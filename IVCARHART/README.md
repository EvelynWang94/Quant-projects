# 🧠 IVCARHART: Residual Volatility Factor Construction and Backtest

This project implements the construction and backtesting of an **idiosyncratic volatility factor (IVCARHART)** using rolling Carhart four-factor regressions on high-frequency stock data.

## 📌 Project Overview

- **Goal**: Measure residual (unexplained) volatility of individual stocks and test its predictive power on future returns.
- **Method**: Estimate residuals from rolling OLS regressions against Carhart 4-factor model, then compute their 21-day rolling standard deviation as daily idiosyncratic volatility.
- **Backtest**: Daily-rebalanced long-short strategy based on IVCARHART ranking (Q1 vs. Q10), accounting for realistic transaction costs.

## 📈 Methodology

### 1. Factor Construction

- Use 21-day rolling window to run stock-level regressions:
  
  $$
  r_{i,t} = \alpha_i + \beta_i MKT_t + s_i SMB_t + h_i HML_t + m_i MOM_t + \epsilon_{i,t}
  $$

- Residual standard deviation scaled by √243 gives annualized **IVCARHART**.

### 2. Factor Definitions

- **MKT**: Value-weighted return of all stocks (market return)
- **SMB**: Small-minus-Big, based on circulating market cap
- **HML**: High-minus-Low, based on PB ratio (BM)
- **MOM**: Winner-minus-Loser, based on prior 21-day return

All factors are constructed **monthly** using end-of-month data.

### 3. Backtest

- **Strategy**: Daily rebalance, 10-quantile sort on IVCARHART  
  - Long Q1 (lowest residual vol), short Q10 (highest residual vol)
- **Execution**: Simulated using VWAP price  
- **Costs**: 0.3% round-trip trading fee, daily turnover accounted


## 📂 Folder Structure

```text
.
├── factor_construction.ipynb     # Main notebook
├── data/
│   ├── daily_post_data.csv
│   ├── pb_ratio_data.csv
│   └── start_date_data.csv
├── figs/
│   └── decile_cumret.png
├── README.md
