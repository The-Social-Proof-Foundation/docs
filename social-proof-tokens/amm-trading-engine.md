---
icon: chart-line
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# AMM Trading Engine

The Automated Market Maker (AMM) trading engine provides continuous liquidity for Social Proof Tokens using quadratic pricing curves and rug-pull resistant design. This system enables **sub-second transaction processing** and **high-volume trading support** optimized for social media-driven economies.

## How the AMM Works

### Continuous Liquidity Model
Unlike traditional order books that require matching buyers and sellers, the AMM provides **always-available liquidity** through algorithmic pricing:

- **Immediate Execution**: Trades execute instantly without waiting for counterparties
- **Price Discovery**: Mathematical curves automatically adjust prices based on supply and demand
- **Scalable Liquidity**: System handles high transaction volumes without performance degradation
- **24/7 Operation**: Trading available continuously without market hours restrictions
- **Rug-Pull Resistant**: Creators cannot manipulate their own token markets

### Rug-Pull Protection

**Creator Revenue Model:**
- **Fee-Based Earnings**: Creators earn exclusively through 1.0% trading fees, not token appreciation
- **No Token Holdings**: Creators cannot buy their own tokens, eliminating pump-and-dump schemes
- **Sustainable Incentives**: Revenue tied to trading activity, encouraging genuine community building
- **Market Integrity**: All price movements reflect genuine external demand

**Built-In Safeguards:**
- **Self-Trading Prevention**: Smart contracts block creators from purchasing their own tokens
- **Transparent Mechanics**: All trading rules publicly visible and immutable
- **Community Protection**: Token holders protected from creator manipulation
- **Fair Discovery**: Prices determined purely by community demand and mathematical curves

## Quadratic Pricing Formula

### Mathematical Implementation
The AMM uses a quadratic pricing curve that creates natural price appreciation as token supply increases:

```
Price = Base Price + (Quadratic Coefficient × Supply²)
```

**Default Parameters:**
- **Base Price**: 0.1 MySo (100,000,000 smallest units)
- **Quadratic Coefficient**: 100,000 (adjustable by governance)

### Price Calculation Examples

**Low Supply Pricing:**
- Supply: 100 tokens
- Price = 0.1 + (0.0001 × 100²) = 0.1 + 1 = 1.1 MySo per token

**Medium Supply Pricing:**
- Supply: 1,000 tokens  
- Price = 0.1 + (0.0001 × 1,000²) = 0.1 + 100 = 100.1 MySo per token

**High Supply Pricing:**
- Supply: 5,000 tokens
- Price = 0.1 + (0.0001 × 5,000²) = 0.1 + 2,500 = 2,500.1 MySo per token

### Curve Benefits
**Natural Market Dynamics:**
- **Early Entry Advantage**: Lower prices for early supporters
- **Scarcity Value**: Higher prices reflect increased community interest
- **Anti-Manipulation**: Large purchases require exponentially more capital
- **Sustainable Growth**: Prevents pump-and-dump schemes through pricing resistance

## Trading Mechanics

### Token Purchase Process
**Buy Process:**
1. **Validation**: Check trading not halted, sufficient funds, block list status
2. **Price Calculation**: Calculate total cost using quadratic integration
3. **Fee Deduction**: Apply 1.5% total trading fees
4. **Pool Update**: Add net MySo to pool, mint tokens to buyer
5. **Balance Tracking**: Update holder balances and circulating supply

### Token Sale Process
**Sell Process:**
1. **Validation**: Verify token ownership, sufficient balance
2. **Price Calculation**: Calculate refund using reverse quadratic integration
3. **Fee Deduction**: Apply 1.5% total trading fees
4. **Pool Update**: Remove MySo from pool, burn tokens from seller
5. **Transfer**: Send net refund to seller

### Price Integration Mathematics

**Buy Price Calculation:**
The system integrates the quadratic price curve over the purchase amount to calculate the total cost. Each token in a purchase has a slightly higher price than the previous one, reflecting the increasing supply.

**Sell Price Calculation:**
Selling reverses the integration process, with each token sold receiving the price it would cost to buy at that supply level, minus trading fees.

## Anti-Manipulation Features

### Hold Limits
**Maximum Hold Percentage:**
- **Limit**: 5% of total token supply per wallet
- **Purpose**: Prevents single-wallet market manipulation
- **Dynamic**: Adjusts as total supply changes
- **Enforcement**: Checked on every purchase transaction

### Block List Integration
**Comprehensive Protection:**
- **Bidirectional Blocking**: Blocked users cannot buy tokens from users who blocked them
- **Platform-Level Blocks**: Platform operators can restrict access to malicious users
- **Creator Protection**: Token creators protected from harassment through trading restrictions
- **Real-Time Checks**: Block status verified at transaction time

### Self-Trading Prevention
**Anti-Manipulation Rules:**
- **No Self-Purchases**: Token creators cannot buy their own tokens
- **Prevents Artificial Pumping**: Eliminates fake demand creation
- **Market Integrity**: Ensures all price movements reflect genuine community interest
- **Fair Discovery**: Price appreciation driven only by external demand

## Performance and Scalability

### High-Volume Architecture
The AMM is designed to handle massive trading volumes characteristic of social media platforms:

**Performance Metrics:**
- **Sub-Second Execution**: Trades processed in under 1 second
- **High Throughput**: Supports thousands of concurrent transactions
- **Efficient Storage**: Optimized data structures for rapid access
- **Scalable Indexing**: Fast lookup of token pools and user balances

### Data Structure Optimization
**Efficient Storage Design:**
The system uses optimized data structures for rapid access and minimal blockchain storage overhead.

**Optimized Operations:**
- **Fast Balance Queries**: Instant holder balance lookups
- **Efficient Price Calculations**: Optimized mathematical operations
- **Minimal State Changes**: Reduced blockchain storage overhead
- **Batch Processing**: Multiple operations in single transactions

## Market Dynamics

### Price Movement Patterns
**Natural Appreciation:**
- **Organic Growth**: Prices rise as community interest increases
- **Supply Scarcity**: Limited supply creates upward price pressure
- **Viral Amplification**: Social media virality drives demand spikes
- **Long-Term Value**: Sustained engagement supports price floors

**Market Correction Mechanisms:**
- **Profit Taking**: High prices encourage selling, creating corrections
- **Entry Opportunities**: Corrections provide new entry points for supporters
- **Equilibrium Finding**: Market naturally discovers fair value levels
- **Volatility Management**: Quadratic curve dampens extreme price swings

### Liquidity Management
**Pool Depth:**
- **MySo Reserves**: Pool accumulates MySo from purchases
- **Token Supply**: Circulating tokens represent community ownership
- **Reserve Ratio**: Higher MySo reserves support larger sell orders
- **Liquidity Growth**: Successful tokens naturally build deeper liquidity

**Exit Liquidity:**
- **Always Available**: AMM guarantees ability to sell at mathematical price
- **No Slippage Risk**: Price determined by curve, not order book depth
- **Fair Pricing**: Sellers receive curve-determined value minus fees
- **Market Making**: System provides continuous two-way markets

## Trading Strategy Implications

### For Token Buyers
**Investment Considerations:**
- **Early Entry**: Lower prices for early supporters of promising content/creators
- **Growth Potential**: Viral content/creators can drive significant appreciation
- **Hold Duration**: Longer holds potentially benefit from sustained growth
- **Community Assessment**: Evaluate creator/content long-term potential

**Risk Management:**
- **Quadratic Risk**: Large purchases face exponentially higher prices
- **Market Timing**: Consider entry points relative to viral momentum
- **Diversification**: Spread investments across multiple tokens
- **Exit Strategy**: Plan for profit-taking or stop-loss levels

### For Token Sellers
**Exit Strategies:**
- **Profit Realization**: Take profits after significant appreciation
- **Market Timing**: Consider selling into viral momentum peaks
- **Partial Sales**: Gradual exits maintain position while realizing gains
- **Strategic Holds**: Long-term positions in promising creators

**Price Impact:**
- **Large Sells**: Significant position exits create buying opportunities
- **Market Signals**: Seller behavior influences community sentiment
- **Fee Considerations**: 1.5% trading fees impact short-term trading profitability

The AMM Trading Engine creates a **sophisticated, scalable, and manipulation-resistant** marketplace for Social Proof Tokens, enabling efficient price discovery while maintaining market integrity through mathematical precision and comprehensive security features.

*Emergency trading controls may be activated by governance in exceptional circumstances.* 