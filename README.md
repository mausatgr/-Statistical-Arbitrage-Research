# -Statistical-Arbitrage-Research
Quant Finance Research Project
# Statistical Arbitrage in Cryptocurrency Markets — Quantitative Finance Research Project

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/yomisys/crypto-stat-arb/blob/main/crypto_stat_arb.ipynb#scrollTo=W1FXDlZHxw75)

---

## What this is

A complete quantitative research system that tests momentum and mean-reversion strategies across the top 25 cryptocurrencies.

| Component | Description |
|---|---|
| **Data** | 3+ years daily OHLCV data |
| **Signals** | Momentum and reversal signals |
| **Backtest** | Long-short quintile portfolio |
| **Evaluation** | Sharpe ratio, alpha t-stat, maximum drawdown |
| **Combination** | Walk-forward portfolio construction |

## How to run

Click the **Open in Colab** badge above, then:

**Runtime → Run all**

## Repo structure

```text
project/
├── notebook.ipynb
├── config.py
├── data/
│   └── data_pipeline.py
├── signals/
│   ├── momentum.py
│   └── reversal.py
├── backtester.py
├── evaluator.py
└── requirements.txt
