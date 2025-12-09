---
description: Search for stocks, crypto, or assets by symbol or name
argument-hint: [query] [asset-class]
---

Search for tradeable assets. Parse arguments: query (required), asset-class (optional: stocks/crypto/all, default: stocks).

Use `mcp__alpaca__get_all_assets` with:
- status: "active"
- asset_class: based on argument (us_equity for stocks, crypto for crypto)

If query is provided:
- Filter results by symbol or name matching the query
- Use case-insensitive matching

Display results table:
- Symbol
- Name (if available)
- Exchange
- Asset Class
- Status
- Tradable?
- Marginable?
- Shortable?
- Fractionable?

Show top 20 matches, sorted by relevance.

For each result, show quick actions:
- Get quote: `/alpaca:quote [SYMBOL]`
- Place trade: `/alpaca:trade [SYMBOL]`
- View chart: `/alpaca:chart [SYMBOL]`

If query matches exact symbol, also fetch and show current quote.

Examples:
- `/alpaca:search AAPL` - Search for Apple stock
- `/alpaca:search tesla` - Search for Tesla (matches TSLA)
- `/alpaca:search BTC crypto` - Search for Bitcoin in crypto assets
- `/alpaca:search tech` - Search for symbols/names containing "tech"
