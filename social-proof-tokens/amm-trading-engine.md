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

The Automated Market Maker (AMM) trading engine provides continuous liquidity for Social Proof Tokens using quadratic pricing curves and a rug-pull resistant design. This system enables sub-second transaction processing and high-volume trading, optimized for social media-driven economies.

## How the AMM Works

Unlike traditional order books, the AMM offers always-available liquidity through algorithmic pricing. Key features include:
- Immediate execution: trades execute instantly, no counterparties needed
- Price discovery: mathematical curves adjust prices based on supply and demand
- Scalable liquidity: handles high transaction volumes

- Rug-pull resistant: creators cannot manipulate their own token markets

## Quadratic Pricing Formula

The AMM uses a quadratic pricing curve:

```
Price = Base Price + (Quadratic Coefficient × Supply²)
```

**Default Parameters:**
- Base Price: 0.1 MySo (100,000,000 smallest units)
- Quadratic Coefficient: 100,000 (adjustable by governance)

**Example Calculations:**
- Supply: 100 tokens → Price = 1.1 MySo per token
- Supply: 1,000 tokens → Price = 100.1 MySo per token
- Supply: 5,000 tokens → Price = 2,500.1 MySo per token

## Trading Mechanics

**Buy Process:**
1. Validation: check trading not halted, sufficient funds, block list status
2. Price calculation: quadratic integration for total cost
3. Fee deduction: 1.5% total trading fees
4. Pool update: add net MySo to pool, mint tokens to buyer
5. Balance tracking: update holder balances and circulating supply

**Sell Process:**
1. Validation: verify token ownership, sufficient balance
2. Price calculation: reverse quadratic integration for refund
3. Fee deduction: 1.5% total trading fees
4. Pool update: remove MySo from pool, burn tokens from seller
5. Transfer: send net refund to seller

**Hold Limits:**
- 5% of total token supply per wallet (dynamic, enforced on every purchase)

**Block List Integration:**
- Bidirectional blocking: blocked users cannot buy tokens from users who blocked them
- Platform-level blocks: platform operators can restrict access
- Creator protection: token creators protected from harassment
- Real-time checks: block status verified at transaction time

**Self-Trading Prevention:**
- Token creators cannot buy their own tokens
- Prevents artificial pumping and ensures market integrity

## Performance and Scalability

- Sub-second execution, thousands of concurrent trades supported
- Optimized data structures for fast lookups and minimal blockchain overhead

## Market Dynamics

- Prices rise as community interest increases; quadratic curve dampens volatility
- Liquidity pools grow as tokens are bought; sellers always have exit liquidity at curve-determined prices
- Supports organic growth, profit realization, and fair market discovery

The AMM Trading Engine creates a sophisticated, scalable, and manipulation-resistant marketplace for Social Proof Tokens, enabling efficient price discovery and market integrity.

_Emergency trading controls may be activated by governance in exceptional circumstances._
