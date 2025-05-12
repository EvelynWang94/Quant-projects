# Quant-projects

This repository contains a collection of my independent research projects in quantitative finance, focusing on factor construction, regression modeling, and cross-sectional backtesting.

Each folder documents a specific factor study or trading strategy, implemented in Python using `pandas`, `statsmodels`, and `matplotlib`. Most projects follow a full-cycle workflow: from data processing and factor construction to IC tests and portfolio backtests.

## 📁 Project List

| Project | Description |
|---------|-------------|
| [`IVCARHART`](./IVCARHART/) | Constructs a residual volatility factor based on rolling Carhart four-factor regressions; evaluates return predictability using IC and 10-quantile strategy. |
| [`ValueTiming`](./ValueTiming/) | Combines PB and ROE factors for value investing timing signals; includes regime-based rebalancing. *(WIP)* |
| [`ShortTermMomentum`](./ShortTermMomentum/) | Backtests short-term momentum signals (5–20 day return) under different rebalance frequencies. *(WIP)* |

> Projects marked *(WIP)* are still under development.

## 🛠️ Tech Stack

- Python 3.x
- `pandas`, `numpy`, `statsmodels`, `matplotlib`, `seaborn`
- Jupyter Notebook
- Optional: `joblib`, `numba` for acceleration

## 📬 Contact

Feel free to reach out if you're interested in quant research, factor investing, or systematic trading strategies:

- 💼 [LinkedIn](https://www.linkedin.com/in/yuchen-wang-2aa64327b/)

