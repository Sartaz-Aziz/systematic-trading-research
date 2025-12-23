# systematic-trading-research
Modular Python framework for systematic trading research and backtesting
# Systematic Trading Research (NC State)

A modular Python backtesting and research framework built to evaluate signal-based trading strategies using disciplined out-of-sample testing and risk-adjusted evaluation.

Note: This repository contains a simplified and reviewable version of the project’s structure and research methodology. Certain components (e.g., proprietary data access and team-owned implementation details) are intentionally omitted or abstracted.

---

## What this project does

- Provides a **modular backtesting pipeline** for historical equity strategies
- Supports **feature engineering** from common technical indicators
- Trains and evaluates **signal models** for long/flat (or long/short) decisions
- Produces **out-of-sample performance reports** using return and risk metrics

---

## Core components

- **Data Layer**
  - Ingestion + cleaning
  - Corporate actions handling (as applicable)
  - Unified dataset interface

- **Feature Engineering**
  - Technical indicators (e.g., EMA, MACD, RSI, Stochastic Oscillator, Aroon)
  - Feature scaling / filtering utilities (optional)

- **Modeling / Signals**
  - Baseline rule-based signals
  - ML-based signals (e.g., logistic regression; optional extensions)

- **Backtesting Engine**
  - Walk-forward / rolling evaluation (out-of-sample)
  - Transaction cost hooks (if enabled)
  - Portfolio accounting + position tracking

- **Evaluation**
  - Annualized return, Sharpe ratio, max drawdown
  - Win rate, trade count
  - Strategy comparison via a weighted score (return/risk trade-off)

---

## Methodology (high level)

1. Collect and clean historical price data  
2. Engineer features from technical indicators  
3. Train signal model(s) on an in-sample window  
4. Run **rolling / walk-forward** one-step updates to simulate real-time usage  
5. Evaluate out-of-sample performance using return + risk metrics  
6. Compare strategies across assets using consistent evaluation rules

---

## Example results (illustrative)

Performance varies across assets and time periods. In one representative backtest, a logistic regression signal achieved:

- **~22.7% annualized return**
- **Sharpe ~0.88**
- **Max drawdown ~24.8%**
- **~77 trades**

These results are included to reflect what the framework can produce and are not presented as live trading performance.

---

## Tech stack

- Python, pandas, NumPy
- scikit-learn (modeling)
- matplotlib (plots)

---

## Repository structure

```text
.
├── data/                # (optional) sample data or instructions to obtain data
├── notebooks/           # research notebooks / experiments
├── src/
│   ├── data/            # loaders, preprocessing
│   ├── features/        # indicators, transformations
│   ├── models/          # signal models
│   ├── backtest/        # engine, portfolio accounting
│   └── evaluation/      # metrics, reporting
├── results/             # exported plots / summaries (optional)
└── README.md

---

## Scope and intent

This repository is intended to demonstrate research structure, experimental design, and evaluation discipline rather than provide a production-ready trading system.

