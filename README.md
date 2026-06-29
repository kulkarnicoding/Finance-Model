# Equity Risk Model — Nifty 50 Factor Analysis & VaR Backtesting

A quantitative portfolio risk project built on Indian equity data (Nifty 50), implementing a Carhart four-factor model to decompose portfolio risk exposures, followed by Value at Risk (VaR) estimation and formal backtesting across the COVID-19 market crisis period (2019–2021).

---

## Project structure

```
equity-risk-model/
│
├── data/               # Raw and processed price/factor data
├── notebooks/          # Colab notebooks (see links below)
├── outputs/            # Charts, factor exposure heatmaps, VaR results
└── README.md
```

---

## Part 1 — Factor model & risk decomposition

**Objective:** Identify where portfolio risk is coming from by decomposing returns into systematic (factor-driven) and idiosyncratic components.

**Portfolio:** 10–12 cross-sector Nifty 50 stocks (banking, IT, energy, FMCG, pharma, industrials), equal-weighted.

**Factors used:**
- Market excess return — Nifty 50 returns minus 91-day T-bill rate (RBI)
- SMB (size) — Nifty Smallcap 100 minus Nifty 50 returns
- HML (value) — Nifty 500 Value 50 minus Nifty 500 Growth index returns
- Momentum — Nifty 200 Momentum 30 index returns (Carhart extension)

**Outputs:**
- OLS regression coefficients (factor loadings) per stock
- Portfolio-level factor exposures (weighted average)
- R-squared and residual (idiosyncratic) variance per stock
- Variance decomposition — % of total portfolio risk from each factor
- Factor exposure heatmap across all stocks
- Rolling beta analysis showing how exposures shifted during COVID crash

**Data source:** Yahoo Finance via yfinance, NSE index data

**Time window:** January 2019 – December 2021 (pre-crisis, crash, recovery)

---

## Part 2 — VaR estimation & backtesting

*(In progress)*

Three VaR methodologies implemented on the same portfolio:
- Historical simulation
- Parametric (variance-covariance)
- Monte Carlo simulation

Formal backtesting using the Kupiec proportion of failures (POF) test at 95% and 99% confidence levels, with breach dates visualised against the portfolio return series.

---

## Notebooks

| Notebook | Description |
|----------|-------------|
| [Data pipeline](https://colab.research.google.com/drive/1emJRqobhVzm9csYj6XqWIwRQoDdKY9u5?usp=sharing) | Fetches and processes Nifty 50 stock prices and factor return series |

---

## Key references

- Fama, E. F., & French, K. R. (1993). Common risk factors in the returns on stocks and bonds. *Journal of Financial Economics*, 33(1), 3–56.
- Carhart, M. M. (1997). On persistence in mutual fund performance. *Journal of Finance*, 52(1), 57–82.
- Jorion, P. (2007). *Value at Risk: The New Benchmark for Managing Financial Risk* (3rd ed.). McGraw-Hill.

---

## Status

- [x] Data pipeline — price fetching, return computation, factor series construction
- [ ] Factor regressions per stock
- [ ] Portfolio aggregation and variance decomposition
- [ ] VaR estimation (three methods)
- [ ] Backtesting and Kupiec test
- [ ] Visualizations and final write-up

---

*Built as part of a quantitative finance project during summer 2025. Part of an ongoing effort to apply financial risk frameworks to Indian equity markets.*
