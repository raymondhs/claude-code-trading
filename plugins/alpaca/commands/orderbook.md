---
description: View cryptocurrency orderbook with bid/ask depth
argument-hint: [crypto-symbol]
---

Display real-time orderbook for cryptocurrency pairs. Parse argument: crypto symbol (e.g., BTC/USD, ETH/USD).

Use `mcp__alpaca__get_crypto_latest_orderbook` to fetch orderbook data.

Display format:

**Market Depth for [SYMBOL]**
Timestamp: [timestamp]

```
ASKS (Sell Orders)
Price         Size          Total
----------------------------------------
$XX,XXX.XX    X.XXXX       $XX,XXX.XX
$XX,XXX.XX    X.XXXX       $XX,XXX.XX
...

-------- SPREAD: $X.XX --------

BIDS (Buy Orders)
Price         Size          Total
----------------------------------------
$XX,XXX.XX    X.XXXX       $XX,XXX.XX
$XX,XXX.XX    X.XXXX       $XX,XXX.XX
...
```

Show:
- Best bid and ask prices (Level 1)
- Order book depth (multiple price levels)
- Bid-ask spread
- Cumulative size at each level
- Total liquidity on each side

Analysis:
- Market sentiment (bid/ask ratio)
- Liquidity depth
- Support/resistance levels from order book

If no argument provided, ask for crypto symbol or show popular symbols: BTC/USD, ETH/USD, SOL/USD, AVAX/USD.

Examples:
- `/alpaca:orderbook BTC/USD` - View Bitcoin orderbook
- `/alpaca:orderbook ETH/USD` - View Ethereum orderbook
