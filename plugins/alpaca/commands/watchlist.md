---
description: Manage watchlists (view, create, update, add/remove symbols)
argument-hint: [action] [name] [symbols]
---

Manage trading watchlists. Parse arguments: action (list/create/add/remove/delete), watchlist name, symbols.

Actions:

1. **list** (default if no args):
   - Use `mcp__alpaca__get_watchlists` to show all watchlists
   - Display: Name, ID, Symbols in each list
   - Show current prices for symbols in watchlists

2. **create [name] [symbols]**:
   - Use `mcp__alpaca__create_watchlist` with name and symbols
   - Example: `/alpaca:watchlist create "Tech Stocks" AAPL,MSFT,GOOGL`

3. **add [name/id] [symbol]**:
   - Find watchlist by name or ID
   - Use `mcp__alpaca__add_asset_to_watchlist_by_id`
   - Example: `/alpaca:watchlist add "Tech Stocks" NVDA`

4. **remove [name/id] [symbol]**:
   - Find watchlist by name or ID
   - Use `mcp__alpaca__remove_asset_from_watchlist_by_id`
   - Example: `/alpaca:watchlist remove "Tech Stocks" AAPL`

5. **delete [name/id]**:
   - Confirm with user
   - Use `mcp__alpaca__delete_watchlist_by_id`

6. **view [name/id]**:
   - Use `mcp__alpaca__get_watchlist_by_id`
   - Show detailed view with current prices and % changes

Display watchlist with:
- Symbols and current prices
- % change today
- Quick actions available

Examples:
- `/alpaca:watchlist` - List all watchlists
- `/alpaca:watchlist create "Growth" TSLA,NVDA,AMD`
- `/alpaca:watchlist add "Growth" PLTR`
- `/alpaca:watchlist view "Growth"` - View with live prices
