---
description: View detailed information about open positions
argument-hint: [symbol]
---

Display positions with profit/loss details. If symbol provided, show specific position. Otherwise, show all positions.

Steps:
1. If symbol argument provided:
   - Use `mcp__alpaca__get_open_position` for detailed single position
   - Show: Quantity, Entry Price, Current Price, Market Value, P/L ($), P/L (%)

2. If no argument:
   - Use `mcp__alpaca__get_all_positions` for all positions
   - Show table with all positions including total P/L summary

Display format:
- Symbol
- Quantity (Long/Short)
- Avg Entry Price
- Current Price
- Market Value
- Unrealized P/L ($)
- Unrealized P/L (%)
- Change Today ($ and %)

Calculate and show:
- Total Unrealized P/L across all positions
- Total Market Value
- Best/Worst performers

If no positions, suggest viewing `/alpaca:portfolio` or placing a trade with `/alpaca:trade`.

Examples:
- `/alpaca:positions` - View all positions
- `/alpaca:positions AAPL` - View AAPL position details
