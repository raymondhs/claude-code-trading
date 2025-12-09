---
description: Exercise held option contracts to convert to underlying asset
argument-hint: [option-symbol]
---

Exercise option contracts you own. Parse argument: option symbol or contract ID.

**Important:** Exercising an option converts it to the underlying stock position:
- **Call option**: You buy 100 shares per contract at the strike price
- **Put option**: You sell 100 shares per contract at the strike price

Steps:
1. If argument provided (option symbol), use it. Otherwise:
   - Use `mcp__alpaca__get_all_positions` to show held options
   - Ask which option to exercise

2. Show option details before exercising:
   - Use `mcp__alpaca__get_option_snapshot` for current data
   - Display:
     * Option symbol and type (Call/Put)
     * Underlying symbol
     * Strike price
     * Expiration date
     * Quantity held
     * Current price
     * Intrinsic value (Current - Strike for calls, Strike - Current for puts)
     * Days until expiration

3. Calculate and show exercise implications:
   - **For Calls**: Cost = Strike Price × 100 × Quantity
   - **For Puts**: Proceeds = Strike Price × 100 × Quantity
   - Check if option is in-the-money
   - Warn if exercising out-of-the-money (unusual)
   - Show required buying power for calls

4. Confirm exercise action:
   - Clearly state the action (buying/selling shares at strike)
   - Show cost or proceeds
   - Confirm user wants to proceed

5. Execute with `mcp__alpaca__exercise_options_position`

6. Show result:
   - Exercise confirmation
   - New stock position details
   - Account impact (cash used/received)

**Notes:**
- Options are typically exercised when in-the-money near expiration
- Most traders close options positions rather than exercising
- Exercising requires sufficient buying power for calls
- American-style options can be exercised anytime before expiration

Examples:
- `/alpaca:exercise AAPL250613C00150000` - Exercise specific AAPL call option
- `/alpaca:exercise` - Interactive: show held options and choose which to exercise
