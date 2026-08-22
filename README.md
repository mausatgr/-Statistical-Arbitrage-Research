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
Medium- and long-horizon momentum generated the strongest historical performance. The best individual strategy was 30-day volume-weighted momentum (`vwmom30d`), which produced a 44.92% annualised net return and a 0.74 Sharpe ratio after 20 bps one-way transaction costs. However, its Sharpe ratio declined from 1.95 during the 2021–2022 training period to 0.14 during the 2023–2025 validation period, representing approximately 92.8% Sharpe decay.

**Mean Reversion**

Short-horizon reversal and statistical-arbitrage strategies performed poorly after transaction costs. Their Sharpe ratios ranged from -0.57 to -0.88, while maximum drawdowns ranged from approximately -95.90% to -99.85%. The results suggest that the potential gross mean-reversion effect was insufficient to overcome adverse returns and transaction costs under the 20 bps market-order assumption.

**Portfolio Combination**

**Portfolio Combination**

Quarterly walk-forward combinations produced more credible out-of-sample results than relying on a single full-sample winner. The inverse-volatility portfolio achieved a 31.85% annualised return, a 0.64 Sharpe ratio, a -62.59% maximum drawdown and a 50.8% win rate. The equal-weighted portfolio achieved a 31.23% annualised return and a 0.63 Sharpe ratio. The Sharpe-weighted portfolio performed less effectively, with a 0.41 Sharpe ratio and a -69.82% maximum drawdown.

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
