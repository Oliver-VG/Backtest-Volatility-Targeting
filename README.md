# Backtest-Volatility-Targeting
Backtesting strategy using volatility-targeted moving average signals for SPY ETF.

This Jupyter Notebook implements a **backtesting strategy** for the SPY ETF using a **volatility-targeted moving average crossover system**. It includes signal generation, dynamic position sizing based on rolling volatility, and performance evaluation including transaction costs.

## Strategy Highlights
- **Asset**: SPY (S&P 500 ETF)
- **Indicators**:
  - Short-term EMA
  - Long-term EMA
  - SMA (price confirmation)
  - Realized volatility (20-day rolling std)
- **Entry Signal**: `Short EMA > Long EMA` and `Price > SMA`
- **Exit Signal**: `Short EMA < Long EMA`
- **Position Sizing**: Scaled to target annualized volatility (default: 15%)
- **Transaction Costs**: Included at 5bps (0.0005)

## Libraries Used
- `yfinance` for historical price data
- `pandas` and `numpy` for data manipulation
- `matplotlib` for visualization

## Features
- Rolling volatility estimation using daily returns
- Scaling factor to adjust position exposure dynamically
- Capped scaling to prevent overexposure
- Portfolio performance visualization

## Parameters
| Parameter              | Default        | Description                            |
|------------------------|----------------|----------------------------------------|
| `symbol`               | `'SPY'`        | Ticker symbol for the asset            |
| `start_date`           | `'2018-01-01'` | Start of the backtest period           |
| `end_date`             | `'2024-01-01'` | End of the backtest period             |
| `short_ema_window`     | `10`           | Short-term EMA window                  |
| `long_ema_window`      | `20`           | Long-term EMA window                   |
| `price_sma_window`     | `20`           | Simple Moving Average window           |
| `volatility_lookback`  | `20`           | Lookback window for realized volatility|
| `target_volatility`    | `0.15`         | Target annualized volatility           |
| `transaction_cost`     | `0.0005`       | One-way transaction cost (0.05%)       |

## Sample Output
- Strategy equity curve
- Signal positioning chart
- Volatility and scaling factor plot


## Getting Started
1. Clone this repo
2. Install dependencies:
   ```bash
   pip install yfinance pandas numpy matplotlib
   ```
3. Open the notebook:
   ```bash
   jupyter notebook backtest-volatility-targeting.ipynb


## Future Enhancements
- Add Sharpe ratio and drawdown analysis
- Include benchmark comparison
- Support for multi-asset portfolios
