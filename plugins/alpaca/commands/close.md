---
description: Close a position or all positions
argument-hint: [symbol|all] [quantity|percentage]
---

Close positions safely with confirmation. Parse arguments: symbol/all (required), quantity or percentage (optional, default: 100%).

Steps:
1. If argument is "all":
   - Use `mcp__alpaca__get_all_positions` to show what will be closed
   - Calculate total value being liquidated
   - Confirm with user
   - Use `mcp__alpaca__close_all_positions`

2. If symbol provided:
   - Use `mcp__alpaca__get_open_position` to show current position
   - If quantity/percentage argument:
     - Parse it (e.g., "50%" or "10" shares)
     - Use `mcp__alpaca__close_position` with qty or percentage parameter
   - If no quantity/percentage:
     - Close entire position with `mcp__alpaca__close_position`
   - Confirm action with user before executing

Show:
- Position details before closing
- Expected proceeds
- Realized P/L after closing
- Updated portfolio value

Examples:
- `/alpaca:close AAPL` - Close entire AAPL position
- `/alpaca:close TSLA 10` - Close 10 shares of TSLA
- `/alpaca:close NVDA 50%` - Close 50% of NVDA position
- `/alpaca:close all` - Close all positions
