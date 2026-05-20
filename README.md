# Algorithmic Forex Trading (Personal Project)

**Ongoing personal project** building Forex trading algorithms in **PineScript** (TradingView) and transitioning to **Python (pandas) vectorized backtesting** to formally validate strategies before any live deployment.

> Not coursework. This is a hobby project that grew out of a deep interest in **quantitative finance** alongside my BS Data Science studies at UA&P.

## What's in this repo (planned)

This repo is in **early-stage active development**. I'm currently transferring strategies from PineScript to Python-based backtesting frameworks.

- `pinescript/` — TradingView strategy scripts, lot-size calculators (to be uploaded).
- `python/` — Python backtesting code (in progress).
  - `backtest/` — Vectorized backtesting harness (pandas-based).
  - `strategies/` — Strategy implementations.
  - `indicators/` — Custom technical indicators.
- `notebooks/` — Exploratory notebooks: indicator behavior, walk-forward analysis, parameter sweeps.

## Approach

1. **Prototype in PineScript** for quick iteration and TradingView's built-in backtester.
2. **Re-implement in Python** for rigorous vectorized backtesting (avoid look-ahead bias, slippage modeling, walk-forward validation).
3. **Paper-trade / forward-test** on demo or micro account before any live capital commitment.

## Status

- ✅ Several PineScript strategy scripts written (lot-size calculators, multiple entry / exit rule systems)
- 🚧 Python backtesting framework being built
- ⏸️ **No strategies deployed to live trading.** Pre-deployment validation in progress.

## Stack

`PineScript` (TradingView) · `Python` · `pandas` · `numpy` · `matplotlib`

## Relevant academic work

My **Time Series Analysis** course final project applies similar methodologies (ARIMA-GARCH + deep learning) to forecasting the USD/PHP exchange rate — see [usdphp-forecasting](https://github.com/riegodavid-git/usdphp-forecasting).

---

**David Nathaniel P. Riego** · BS Data Science, UA&P (Aug 2023 – Aug 2027 expected) · [LinkedIn](https://linkedin.com/in/david-riego/)
