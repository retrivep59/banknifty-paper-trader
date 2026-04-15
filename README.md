# BankNifty Paper Trader

A BankNifty F&O paper trading simulator with real NSE/Yahoo Finance data, a live TUI dashboard, and an automated signal agent.

## Features

- **Live data** — 5-min candles via Yahoo Finance + NSE delayed quote
- **TUI dashboard** — full-screen terminal UI (Textual/Rich) with real-time P&L, indicators, trade log
- **Trading agent** — EMA crossover + RSI + MACD + Bollinger Bands signal logic
- **Paper broker** — realistic fills with STT, brokerage, exchange fees
- **Backtest** — replay 30 days of real BankNifty data with full reporting

## Quick Start

```bash
pip install -r requirements.txt

# TUI dashboard (demo mode — no internet needed)
python dashboard.py --demo

# TUI dashboard with live NSE data
python dashboard.py --live

# Command-line live paper trading
python run_live.py --capital 500000 --instrument FUTURES

# 30-day backtest
python backtest_30d.py --capital 500000
```

## Project Structure

```
agent/          BankNiftyAgent — signal generation
broker/         PaperBroker — order execution + P&L tracking
data/           LiveFeed — Yahoo Finance + NSE live quote
simulation/     SimulationEngine — backtest harness
dashboard.py    Textual TUI dashboard
run_live.py     CLI live trading runner
backtest_30d.py 30-day historical backtest
config.py       Instrument + fee constants
```

## Instruments

| Key       | Description                  |
|-----------|------------------------------|
| `FUTURES` | BankNifty monthly futures    |
| `CE`      | ATM call option (weekly)     |
| `PE`      | ATM put option (weekly)      |

## Dashboard Controls

| Key | Action         |
|-----|----------------|
| `q` | Quit           |
| `d` | Demo mode      |
| `l` | Live mode      |
| `b` | Backtest mode  |

## Disclaimer

For educational and research purposes only. Not financial advice. Paper trading only — no real money is placed.
