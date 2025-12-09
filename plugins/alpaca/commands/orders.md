---
description: View open, closed, or all orders with filtering options
argument-hint: [status] [limit]
---

Display orders with optional filtering. Parse arguments: status (open/closed/all, default: open), limit (default: 10).

Use `mcp__alpaca__get_orders` with parameters:
- status: from argument
- limit: from argument or default to 10

Show formatted table with:
- Symbol
- Side (Buy/Sell)
- Quantity
- Type (Market/Limit/Stop/etc.)
- Status
- Limit Price (if applicable)
- Filled Quantity / Filled Average Price
- Submission Time
- Order ID (last 8 chars for readability)

If no orders found, suggest using `/alpaca:trade` to place an order.

Examples:
- `/alpaca:orders` - View open orders
- `/alpaca:orders all 20` - View last 20 orders (any status)
- `/alpaca:orders closed 5` - View last 5 closed orders
