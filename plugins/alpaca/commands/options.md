---
description: View options contracts and place options trades
argument-hint: [symbol] [expiration]
---

Help user explore and trade options. If arguments provided, use them. Otherwise, ask for symbol and optionally expiration.

Steps:
1. Use `mcp__alpaca__get_option_contracts` to find available contracts
   - Filter by expiration if specified (use expiration_expression for natural language)
   - Show calls and puts separately

2. Display contracts in a table:
   - Strike price
   - Type (Call/Put)
   - Expiration date
   - Symbol

3. If user wants to see pricing:
   - Use `mcp__alpaca__get_option_snapshot` for quote, Greeks, and implied volatility
   - Show bid/ask, delta, gamma, theta, vega, rho, IV

4. If user wants to trade:
   - Confirm contract details
   - Use `mcp__alpaca__place_option_market_order` with proper legs format
   - Show order confirmation

Examples:
- `/alpaca:options AAPL` - View all available AAPL options
- `/alpaca:options NVDA "week of September 2, 2025"` - View NVDA options for specific week
