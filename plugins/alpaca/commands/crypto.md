---
description: Trade cryptocurrency (buy/sell with USD or notional amounts)
argument-hint: [symbol] [buy|sell] [amount]
---

Trade cryptocurrency with Alpaca. Parse arguments: symbol (e.g., BTC/USD, ETH/USD), side (buy/sell), amount.

**Key Differences from Stock Trading:**
- Can buy with dollar amounts (notional) OR quantity
- Time-in-force: GTC (good-til-canceled) or IOC (immediate-or-cancel) only
- No extended hours flag
- 24/7 trading availability

Steps:
1. If arguments provided, use them. Otherwise, ask for:
   - Symbol (e.g., BTC/USD, ETH/USD, DOGE/USD)
   - Side (buy or sell)
   - Amount (can be dollar amount like "$100" or quantity like "0.5")

2. Before placing order:
   - Use `mcp__alpaca__get_crypto_snapshot` to show current price
   - Calculate expected quantity/cost
   - Show market data

3. Confirm trade details:
   - Symbol and current price
   - Side and amount
   - Order type (default: market)
   - Time in force (default: GTC)
   - Estimated cost/proceeds

4. Execute with `mcp__alpaca__place_crypto_order`:
   - If amount starts with "$", use notional parameter
   - Otherwise, use qty parameter
   - Default: market order, time_in_force="gtc"

5. Show order confirmation with fill details

Examples:
- `/alpaca:crypto BTC/USD buy $1000` - Buy $1000 worth of Bitcoin
- `/alpaca:crypto ETH/USD buy 0.5` - Buy 0.5 Ethereum
- `/alpaca:crypto DOGE/USD sell 100` - Sell 100 Dogecoin
- `/alpaca:crypto` - Interactive mode, asks for all details
