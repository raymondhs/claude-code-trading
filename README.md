# Alpaca Trading with Claude Code

Learning algorithmic trading with Alpaca Markets using the Alpaca MCP Server and Claude Code.

## Prerequisites

Install and configure the Alpaca MCP Server (provides trading tools):

```bash
# Install and initialize (creates .env with API keys)
uvx alpaca-mcp-server init

# Register with Claude Code
claude mcp add alpaca --scope user --transport stdio uvx alpaca-mcp-server serve \
  --env ALPACA_API_KEY=your_alpaca_api_key \
  --env ALPACA_SECRET_KEY=your_alpaca_secret_key

# Verify MCP server is registered
claude mcp list
```

## Installation

Install the Alpaca plugin (provides slash commands) inside Claude Code:

```bash
# Add plugin marketplace
/plugin marketplace add raymondhs/claude-code-trading

# Install Alpaca plugin
/plugin install alpaca@claude-code-trading
```

## Available Commands

### Market Data
- `/alpaca:quote AAPL` - Get real-time quote
- `/alpaca:chart AAPL 1Hour 5` - Historical price bars
- `/alpaca:search tesla` - Search for assets
- `/alpaca:market` - Market hours and calendar
- `/alpaca:corporate AAPL` - Corporate actions (splits, dividends)

### Portfolio Management
- `/alpaca:portfolio` - Complete account overview
- `/alpaca:positions` - View all positions
- `/alpaca:performance 1M` - Portfolio performance analysis

### Trading
- `/alpaca:stock AAPL buy 10` - Place stock order
- `/alpaca:crypto BTC/USD buy 100` - Trade crypto
- `/alpaca:options AAPL` - Options trading
- `/alpaca:exercise AAPL250613P00205000` - Exercise options

### Order Management
- `/alpaca:orders open` - View orders
- `/alpaca:cancel <order_id>` - Cancel order
- `/alpaca:close AAPL` - Close position

### Watchlists
- `/alpaca:watchlist` - Manage watchlists
- `/alpaca:orderbook BTC/USD` - Crypto orderbook

## Learning Path

1. **Explore Market Data** - Use quote, chart, and market commands
2. **Paper Trading** - Practice with `/alpaca:stock` and `/alpaca:crypto`
3. **Portfolio Analysis** - Track performance with `/alpaca:portfolio`
4. **Advanced Strategies** - Options trading and automated strategies

## Resources

- [Alpaca MCP Server](https://github.com/alpacahq/alpaca-mcp-server)
- [Alpaca Markets Docs](https://docs.alpaca.markets/)
- [Alpaca Python SDK](https://alpaca.markets/sdks/python/)
- [Paper Trading Dashboard](https://app.alpaca.markets/paper/dashboard/overview)

## Notes

- Always use **paper trading** (`ALPACA_PAPER=true`) while learning
- Commands provide direct access to Alpaca API through Claude Code
- Build custom trading strategies by combining commands

---

**Status:** Learning and experimenting with algo trading
