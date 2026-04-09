# Financial Data Pipeline & Analytics System

A Python-based quantitative finance pipeline that ingests OHLCV price data, engineers a rich set of technical indicators, and evaluates portfolio performance using industry-standard risk-adjusted metrics.

---

## Overview

This project simulates two years of daily stock price data for five major tech equities using Geometric Brownian Motion (GBM), computes 19 technical features per ticker, constructs an equal-weight portfolio, and evaluates its performance across return, risk, and efficiency dimensions. The pipeline is designed to be modular and scalable — swap in real market data from `yfinance` with a single line change.

---

## Results

An equal-weight portfolio across AAPL, MSFT, GOOGL, AMZN, and TSLA over a 2-year simulation window produced the following results:

| Metric | Value |
|---|---|
| Annual Return | +19.06% |
| Annual Volatility | 10.49% |
| Sharpe Ratio | 1.436 |
| Max Drawdown | -5.50% |
| Calmar Ratio | 3.468 |
| Features engineered | 19 per ticker |
| Tickers tracked | 5 (scalable to 500+) |

A Sharpe Ratio of 1.436 is well above the 1.0 threshold considered strong for a risk-adjusted strategy. The portfolio's Max Drawdown of just -5.50% and Calmar Ratio of 3.468 confirm excellent downside control relative to returns.

---

## Features

**Data Simulation**
- Geometric Brownian Motion (GBM) price simulation for realistic OHLCV data
- Easily replaceable with real data via `yfinance.download()`

**Technical Indicator Engineering (19 features per ticker)**
- RSI (14-period) — momentum oscillator
- MACD, Signal Line, Histogram — trend-following momentum
- EMA 20 / 50 / 200 — short, mid, and long-term trend filters
- Bollinger Bands (Upper, Lower, Width) — volatility bands
- ATR (14-period) — absolute daily price range measure
- Log Returns, 5-day Rolling Volatility, 10-day Momentum

**Portfolio Analytics**
- Equal-weight or custom-weight portfolio construction
- Annualised return and volatility
- Sharpe Ratio (vs. 4% risk-free rate)
- Max Drawdown and Calmar Ratio
- Rolling 63-day (quarterly) Sharpe Ratio

**Visualizations**
- Price chart with EMA overlays and Bollinger Bands
- RSI panel with overbought/oversold zones
- MACD with histogram
- Cumulative return with drawdown overlay
- Rolling Sharpe Ratio
- Cross-asset return correlation heatmap

---
