---
description: View historical price data and charts for a stock or crypto
argument-hint: [symbol] [timeframe] [period]
---

Display historical price bars for analysis. Parse arguments: symbol (required), timeframe (optional, default: 1Day), period (optional, default: 1 month).

Use `mcp__alpaca__get_stock_bars` with parameters:
- symbol: from argument
- timeframe: e.g., "1Min", "5Min", "1Hour", "1Day"
- days: calculate based on period requested

Show formatted table with:
- Timestamp
- Open, High, Low, Close
- Volume
- Price change from previous bar

For crypto, use `mcp__alpaca__get_crypto_bars`.

Examples:
- `/alpaca:chart AAPL` - Daily bars for 1 month
- `/alpaca:chart TSLA 1Hour 5` - Hourly bars for 5 days
- `/alpaca:chart BTC/USD 15Min 1` - 15-min crypto bars for 1 day
