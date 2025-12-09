---
description: Cancel open orders (specific order or all)
argument-hint: [order_id|all]
---

Cancel orders safely with confirmation. If argument is "all", cancel all open orders. If order_id provided, cancel that specific order. Otherwise, show open orders and ask which to cancel.

Steps:
1. If argument is "all":
   - Use `mcp__alpaca__get_orders` with status="open" to show what will be canceled
   - Confirm with user
   - Use `mcp__alpaca__cancel_all_orders`

2. If order_id provided:
   - Use `mcp__alpaca__cancel_order_by_id` with the order_id

3. If no argument:
   - Use `mcp__alpaca__get_orders` with status="open"
   - Ask user which order to cancel (show Order IDs)
   - Use `mcp__alpaca__cancel_order_by_id`

Always confirm cancellation result and show updated order status.

Examples:
- `/alpaca:cancel all` - Cancel all open orders
- `/alpaca:cancel abc123def` - Cancel specific order by ID
- `/alpaca:cancel` - Interactive: show orders and ask which to cancel
