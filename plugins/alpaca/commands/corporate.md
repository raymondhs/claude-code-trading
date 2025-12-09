---
description: View corporate actions (splits, dividends, mergers) for stocks
argument-hint: [symbols] [start-date] [end-date]
---

Display corporate actions affecting stocks. Parse arguments: symbols (comma-separated, optional), start-date (default: 30 days ago), end-date (default: 30 days ahead).

Use `mcp__alpaca__get_corporate_actions` with:
- symbols: from argument (if provided)
- start: start-date
- end: end-date
- limit: 100

Show corporate actions by type:

**Stock Splits:**
- Forward Split (e.g., 2-for-1)
- Reverse Split (e.g., 1-for-10)
- Unit Split

**Dividends:**
- Cash Dividend
- Stock Dividend

**Mergers & Acquisitions:**
- Cash Merger
- Stock Merger
- Stock and Cash Merger

**Other:**
- Spin-offs
- Name Changes
- Rights Distribution
- Redemptions

Display table:
- Symbol
- Action Type
- Announcement Date
- Ex-Date
- Record Date
- Payment Date
- Details (split ratio, dividend amount, etc.)

Highlight upcoming actions (ex-date in future).

Examples:
- `/alpaca:corporate` - All corporate actions, 30 days past to 30 days future
- `/alpaca:corporate AAPL,MSFT` - Corporate actions for specific stocks
- `/alpaca:corporate AAPL 2025-01-01 2025-12-31` - AAPL actions for 2025
