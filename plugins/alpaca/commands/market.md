---
description: View market calendar and trading hours
argument-hint: [start-date] [end-date]
---

Display market calendar and trading schedule. Parse arguments: start-date (default: today), end-date (default: 2 weeks from start).

Use these tools:
1. `mcp__alpaca__get_clock` - Current market status and next open/close times
2. `mcp__alpaca__get_calendar` - Market calendar for date range

Show:
- Current market status (Open/Closed)
- Current time and timezone
- Next market open/close times
- Today's trading session times (if market day)
- Upcoming market days in the specified range
- Upcoming market holidays/closures

Format calendar as table:
- Date
- Day of Week
- Market Open Time
- Market Close Time
- Early Close? (if applicable)

Highlight important dates:
- Today
- Early close days
- Upcoming holidays

Examples:
- `/alpaca:market` - View today's status and next 2 weeks
- `/alpaca:market 2025-12-01 2025-12-31` - View December 2025 calendar
