---
description: Analyze portfolio performance over time
argument-hint: [period] [timeframe]
---

Display portfolio performance metrics and history. Parse arguments: period (default: 1M), timeframe (default: 1D).

Period options: 1W, 1M, 3M, 6M, 1Y, all
Timeframe options: 1Min, 5Min, 15Min, 1H, 1D

Use `mcp__alpaca__get_portfolio_history` with:
- period: from argument
- timeframe: from argument
- intraday_reporting: "continuous"

Display:
- Performance chart (text-based or table)
- Key metrics:
  - Starting Equity
  - Current Equity
  - Total Return ($)
  - Total Return (%)
  - Highest Equity (Peak)
  - Lowest Equity (Trough)
  - Max Drawdown (%)
  - Number of data points

Show data table:
- Date/Time
- Equity
- Profit/Loss
- P/L %

Calculate additional metrics:
- Average daily return
- Volatility (standard deviation of returns)
- Best day / Worst day
- Number of positive vs negative days

Examples:
- `/alpaca:performance` - Last month, daily data
- `/alpaca:performance 1Y 1D` - Last year, daily data
- `/alpaca:performance 1W 1H` - Last week, hourly data
