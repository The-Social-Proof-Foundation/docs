---
icon: coins
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

# Overview

MySocial uses an advanced on-chain trading protocol that merges the precision of Central Limit Order Books (CLOBs) with the continuous liquidity of Automated Market Makers (AMMs). This hybrid model provides deep liquidity, efficient order execution, and the scalability required to support the high transaction volume of a social media-driven economy.

## How it Works

### On-Chain CLOB Matching

MySocial's core order-matching engine runs entirely on-chain, ensuring transparency, verifiability, and decentralization. The CLOB maintains an active list of buy and sell limit orders, matching them based on price-time priority. This guarantees efficient price discovery while ensuring minimal slippage for large orders.

Orders submitted to the MySocial order book are executed based on the following logic:

1. Limit orders are matched if a counterparty order exists at the requested price.
2. If no match exists, the order remains on the book, waiting for execution.
3. If a market order is placed, it will execute against existing orders at the best available price.

### AMM Dedicated Trading for Social Proof Tokens

MySocial incorporates a dedicated AMM (Automated Market Maker) mechanism specifically for trading social proof tokens. Unlike the CLOB which handles traditional asset pairs, the AMM liquidity pools are purpose-built for social token swapping.

This specialized approach ensures that:

* Social Proof Tokens have continuous liquidity through dedicated pools.
* Users can efficiently swap social tokens without relying on order book matching.
* Liquidity providers (LPs) earn fees by supplying assets to these specialized AMM pools.

### Security and Finality

Unlike traditional exchanges that rely on external sequencers or off-chain computation, MySocial executes all trades on-chain, ensuring full transparency and verifiability. The system does not rely on custodial intermediaries, meaning users maintain full control of their assets throughout the trade lifecycle.

Additionally, MySocial:

* Guarantees trade finality on-chain through deterministic execution.
* Prevents transaction frontrunning by utilizing fair transaction ordering.
* Uses the native MYSO token for transaction fees, eliminating the need for external utility tokens.

### Scalability & Performance

The MySocial trading protocol is designed to scale with increasing demand. The order book can process thousands of transactions per second, ensuring rapid order execution even during peak market activity. The dedicated AMM for social tokens enhances the ecosystem's liquidity, making the platform well-suited for high-volume trading driven by social media interactions.

## Conclusion

MySocial's trading engine combines a traditional CLOB with a dedicated AMM system for social tokens. By utilizing the CLOB for standard trading pairs and specialized AMMs for social proof tokens, we ensure both efficiency and continuous liquidity across different asset types. This innovation allows MySocial to support a high-speed, low-cost, decentralized trading experience, perfectly aligned with the needs of a social media-based blockchain ecosystem.

# Social Proof Tokens

Social Proof Tokens are MySocial's **buy and sellable social proof system** that enables users to invest in creators, content, and communities through tokenized social value with dynamic pricing and automated market-making.

## What Social Proof Tokens Actually Do

Social Proof Tokens transform social interactions into **tradeable financial instruments** through:

### 💰 **Tokenized Social Value**
- **Profile Tokens**: Invest directly in creators and their success
- **Post Tokens**: Bet on content virality and engagement
- **Dynamic Pricing**: AMM with quadratic pricing curves
- **Real Trading**: Buy and sell tokens for real MYS value

### 🚀 **Viral Threshold System**
- **Automatic Activation**: Tokens become tradeable when content hits viral metrics
- **Post Thresholds**: Based on likes, comments, and tips (weighted scoring)
- **Profile Thresholds**: Based on followers, posts, and tips received
- **Fair Launch**: Pre-launch auctions ensure equitable distribution

### 📈 **Automated Market Making (AMM)**
- **Quadratic Pricing**: Price increases with demand using mathematical curves
- **Continuous Liquidity**: Always available for trading
- **Base Price**: Starting point for new token pools
- **Dynamic Supply**: Token supply adjusts with market activity

### 💸 **Revenue Distribution**
- **Creator Fees**: 1.0% of trades go to content/profile owner
- **Platform Fees**: 0.25% to hosting platform
- **Treasury Fees**: 0.25% to ecosystem development
- **Total Fees**: 1.5% total trading fees

## How It Works

### 1. Content Creation & Viral Detection
1. User creates post or profile gains traction
2. System tracks engagement metrics (likes, comments, tips, follows)
3. Weighted scoring system calculates viral threshold
4. When threshold met, token becomes eligible for trading

### 2. Pre-Launch Auctions
For fair token distribution:
- **Auction Period**: 1-3 hours for posts, 1-3 days for profiles
- **Community Bidding**: Users contribute MYS to auction pool
- **Fair Allocation**: Tokens distributed proportionally to contributions
- **Price Discovery**: Initial token price set by auction results

### 3. Active Trading
Once launched:
- **Buy Tokens**: Purchase tokens at current AMM price
- **Sell Tokens**: Sell tokens back to AMM pool
- **Price Movement**: Quadratic curve adjusts prices based on supply/demand
- **Fee Distribution**: Trading fees automatically distributed

### 4. PoC Integration
Proof of Creativity affects token economics:
- **PoC Badges**: Enhance token pool credibility and value
- **Revenue Redirection**: Automatically applies to token trading fees
- **Community Confidence**: PoC status influences trading behavior

## Technical Implementation

### Viral Threshold Calculations

**Post Tokens:**
```
Score = (Likes × 1) + (Comments × 3) + (Tips × 10)
Threshold = 100 points
```

**Profile Tokens:**
```
Score = (Followers × 1) + (Posts × 1) + (Tips × 5)
Threshold = 100 points
```

### AMM Pricing Formula
```
Price = Base Price + (Quadratic Coefficient × Supply²)
```

### Fee Distribution (1.5% total)
- **Creator**: 1.0% (to post/profile owner)
- **Platform**: 0.25% (to hosting platform)
- **Treasury**: 0.25% (to ecosystem fund)

### Hold Limits
- **Maximum Hold**: 5% of any token's total supply per wallet
- **Anti-Manipulation**: Prevents single-wallet market control
- **Fair Distribution**: Encourages broad community participation

## Token Types

### Profile Tokens
- **Investment Vehicle**: Bet on creator's long-term success
- **Creator Benefits**: Direct monetization of personal brand
- **Longer Auctions**: 1-3 day auction periods for price discovery
- **Sustained Value**: Based on ongoing creator activity and growth

### Post Tokens
- **Content Speculation**: Invest in viral content potential
- **Immediate Impact**: Quick response to trending content
- **Shorter Auctions**: 1-3 hour auction periods for rapid deployment
- **Event-Driven**: Value tied to specific content performance

## Integration Points

### MyIP Integration
- Token pools can represent access to premium MyIP content
- Revenue from MyIP sales can flow to token holders
- Encrypted content can be gated by token ownership

### Platform Economics
- Platforms earn fees from token trading activity
- Enhanced creator monetization drives platform value
- Community investment creates stronger user engagement

### Social Mechanics
- Token ownership represents community support
- Trading activity indicates content/creator momentum
- Price movements signal market sentiment

## Benefits

### For Creators
- **Direct Monetization**: Earn from personal brand and content value
- **Community Investment**: Fans can financially support success
- **Performance Incentives**: Token value tied to engagement and quality
- **Revenue Streams**: Multiple income sources from single content

### For Investors/Community
- **Social Speculation**: Profit from identifying promising creators/content
- **Community Participation**: Financial stake in favorite creators
- **Early Access**: Get in early on rising creators
- **Liquid Markets**: Always able to buy/sell positions

### For Platforms
- **Revenue Generation**: Earn fees from all token trading
- **User Engagement**: Financial incentives increase platform activity
- **Creator Retention**: Enhanced monetization keeps top creators
- **Network Effects**: Token trading creates viral platform growth

### For the Ecosystem
- **Value Creation**: Transforms social proof into measurable value
- **Fair Economics**: Transparent, algorithmic fee distribution
- **Community Governance**: Token holders have stake in success
- **Innovation Incentives**: Rewards quality content and creators

Social Proof Tokens create a new economy where social value becomes financial value, enabling creators to monetize their influence while giving communities a way to invest in the content and creators they believe in.
