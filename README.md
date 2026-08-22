# Statistical-Arbitrage-Research
# Statistical Arbitrage in Cryptocurrency Markets

### Quantitative Finance Research Project

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/121av8iZ9YOZzSjFkknD2bVE4P5Cf-Um7#scrollTo=W1FXDlZHxw75) This link is publicly viewable

---

## Project Overvie

This project investigates whether momentum and mean-reversion effects can
generate statistically significant returns in cryptocurrency markets.

The research uses daily OHLCV data from the top 25 cryptocurrencies and
evaluates multiple trading signals through a systematic backtesting framework.

---

## Research Question

> Do momentum and mean-reversion signals provide economically and
> statistically significant returns in cryptocurrency markets?

---

## Research Approach

### 01 — Data

- 3+ years of daily OHLCV data
- Cryptocurrency universe defined using 25 Cryptocurrencies
- Data sourced from CCXT/Binance
- Cached locally using Parquet

### 02 — Signal Construction

The research evaluates:

- Momentum signals
- Mean-reversion signals
- Cross-sectional signals
- Volume-weighted signals
- Pairs-trading signals

### 03 — Portfolio Construction

Signals are converted into long-short portfolios using:

- Quintile ranking
- Equal-weighted portfolios
- Inverse-volatility weighting
- Transaction-cost assumptions

### 04 — Performance Evaluation

Strategies are evaluated using:

| Metric | Purpose |
|---|---|
| Sharpe Ratio | Risk-adjusted performance |
| Alpha | Excess return |
| Alpha t-statistic | Statistical significance |
| Maximum Drawdown | Downside risk |

---

## Results

### Key Findings

**Momentum**

Momentum produced positive risk-adjusted returns over the
14–30 day holding horizon.

**Mean Reversion**

Short-horizon reversal signals showed weaker performance and were
more sensitive to transaction costs.

**Portfolio Combination**

Combining signals reduced dependence on any individual strategy and
produced more stable performance.

> **Full results and statistical tests are available in the notebook (Publicly viewable).**

---

## Methodology

The research follows a train/validation framework to reduce the risk of
overfitting.

```text
Historical Data
      │
      ▼
Data Cleaning
      │
      ▼
Signal Construction
      │
      ▼
Portfolio Formation
      │
      ▼
Backtesting
      │
      ▼
Statistical Evaluation
      │
      ▼
Walk-Forward Combination
