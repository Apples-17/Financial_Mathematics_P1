# Financial_Mathematics_P1

# NIFTY50 Trading Strategy Mini-Project

This project implements and evaluates a rule-based trading strategy on a NIFTY50 stock using historical market data from Yahoo Finance.

The objective is to create a strategy that attempts to outperform the Buy-and-Hold approach while satisfying the project constraints:
- Technical indicators implemented from scratch
- Custom backtesting framework
- Performance evaluation using standard financial metrics

---

## Objective

The goal of this project is to:

- Fetch historical stock data using `yfinance`
- Build technical indicators manually without TA-Lib
- Generate trading signals based on market conditions
- Backtest the strategy on historical data
- Compare strategy performance against Buy-and-Hold
- Visualize portfolio growth using an equity curve

---

## Strategy Overview

This strategy combines trend-following, momentum confirmation, and risk management.

### Indicators Used

#### 1. Exponential Moving Average (EMA)
Used to identify the market trend.

- EMA 20 → Short-term trend
- EMA 50 → Long-term trend

EMA gives more weight to recent prices, so it reacts faster than a simple moving average.

---

#### 2. Relative Strength Index (RSI)
Used to measure momentum strength.
 
RSI helps identify whether momentum is strong enough to support a trade.

---

#### 3. Bollinger Bands
Used to measure price volatility and breakout strength.
 
Bollinger Bands expand and contract with volatility, helping detect strong price movement.

---

#### 4. Donchian Low (Trailing Stop)
Used as a dynamic stop-loss mechanism.

It tracks recent lows and helps decide when a trade should be exited.

---

## Trading Logic

### Entry Conditions
A buy position is taken when:
- EMA(20) > EMA(50)
- RSI is within the chosen range
- Price satisfies the strength / breakout condition

### Exit Conditions
A sell position is taken when:
- Price falls below trailing stop
- Or trend weakens / reverses

---

## Backtesting Logic

A custom backtester is implemented to simulate the strategy.

### Features
- Starts with an initial capital
- Buys and sells based on generated signals
- Applies transaction cost of 0.5%
- Tracks:
  - Portfolio value
  - Trade returns
  - Equity curve
  - Final performance metrics

---

## Performance Metrics

The following metrics are calculated:

- **Total Return** → Overall gain or loss from the strategy
- **Annualized Return** → Return scaled to yearly basis
- **Maximum Drawdown** → Largest portfolio fall from peak
- **Sharpe Ratio** → Risk-adjusted return
- **Win Rate** → Percentage of profitable trades
- **Number of Trades** → Strategy activity level

---

## Output

The project generates:

- Indicator-enhanced price dataset
- Trading signals
- Portfolio equity values
- Trade-level results
- Performance summary
- Equity Curve plot
- Buy-and-Hold comparison

---

## Project Structure

```bash
.
├── FM_Project1.ipynb
├── README.md
