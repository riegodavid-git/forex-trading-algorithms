# PineScript Strategies & Indicators

TradingView PineScript v5 / v6 source for the position-sizing tools and discretionary-trade-confirmation indicators I currently use. Paste any file into TradingView's **Pine Editor** to load.

## Files

### `lotsize_calculator.pine` — *LotSize Calculator (psyplo)*
PineScript v5 **indicator** that converts a trade idea (entry, stop loss, take profit) into a position-sized order using account-percentage risk.

- Inputs: account size, risk % per trade, base currency (cross-currency conversion via `request.security` so it works on non-USD pairs), lot size convention, sizing method (lots vs raw QTY).
- Outputs: floating info table with entry / TP / SL / position size / risk / profit / risk-reward ratio, plus on-chart horizontal lines (style + color + visibility per-line configurable).
- Safety: runtime-error guard if TP and SL aren't on opposite sides of entry.

### `macro_session_quarters.pine` — *Macros, Sessions, and Quarters (MSQ)*
PineScript v6 **indicator** that overlays ICT-style intraday structure on any chart.

- **Macro time windows** — auto-drawn boxes around the high/low of the configurable N-minute window before/after each hour.
- **Session ribbon** — color-coded boxes for Asia / London / New York sessions in Asia/Singapore (UTC+8).
- **Session quarters** — auto-split each session into Q1–Q4 (90-minute quarters by default), color-coded.

### `two_sweeps_model.pine` — *TwoSweepsModel (TSM)*
PineScript v6 **multi-timeframe signal indicator** combining liquidity-sweep detection with Fair Value Gap (FVG) confirmation.

- **SFP (Swing Failure Pattern) detection** on 1H and 30m via `request.security`, with pivot-length lookback for prior highs/lows.
- **FVG detection** on the 5m chart with optional Volume / ATR / Trend filters.
- **IFVG (Inverse FVG) confirmation** — when a 5m candle closes through a recent bull/bear FVG after an SFP trigger fires, plots a "Buy" / "Sell" label and emits a TradingView alert (`once_per_bar_close`).
- Designed to display only on a 5m chart; gracefully no-ops on other timeframes.

## Why these are here (and not in `python/`)

PineScript is my **prototyping layer** — fast iteration, instant chart feedback, built-in backtester. The Python directory is where strategies graduate to once they survive rigorous vectorized backtesting (walk-forward, slippage, look-ahead-free splits). Nothing here has been promoted to a live-traded automated strategy yet.

## Author / Attribution

All scripts authored by **David Nathaniel P. Riego** (`@psyplo` on TradingView). Released under **MPL 2.0** as per the headers.
