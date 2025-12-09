---
description: Place a stock order with guided assistance
argument-hint: [symbol] [buy|sell] [quantity]
---

Help the user place a stock order. If arguments are provided (symbol, side, quantity), use them. Otherwise, ask for the details.

Before placing any order:
1. Get current price with `mcp__alpaca__get_stock_latest_quote` and `mcp__alpaca__get_stock_snapshot`
2. Show current market data
3. Confirm trade details explicitly with the user

Once confirmed, execute with `mcp__alpaca__place_stock_order`. Default to market orders with time_in_force="day".

Show order confirmation after execution.
