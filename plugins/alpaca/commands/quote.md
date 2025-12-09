---
description: Get real-time quote and market data for a stock or crypto
argument-hint: [symbol]
---

Get comprehensive market data for a symbol. If argument is provided, use it. Otherwise, ask for the symbol.

Use these tools:
1. `mcp__alpaca__get_stock_latest_quote` for current bid/ask
2. `mcp__alpaca__get_stock_snapshot` for comprehensive data including latest trade, daily bar, and previous day bar

Display:
- Current price and change ($ and %)
- Bid/Ask spread
- Day's range (High/Low)
- Previous close
- Volume
- Timestamp

For crypto symbols (e.g., BTC/USD), use `mcp__alpaca__get_crypto_snapshot` instead.
