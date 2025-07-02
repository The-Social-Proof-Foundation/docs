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

# Token Pool Management

Token Pool Management covers the creation, operation, and lifecycle of Social Proof Token pools. The system is designed for robust liquidity, security, and operational flexibility, supporting high performance for social media-scale trading volumes.

## Pool Architecture

Each token pool maintains essential information, including:
- Ownership details
- MySo reserves
- Holder balances
- Proof of Creativity (PoC) integration

**Pool Types:**
- **Profile Token Pools:**
  - Lower initial supply (premium pricing, limited quantity)
  - Designed for long-term value and sustained creator-fan relationships
  - Extended auction period: 1-3 days
- **Post Token Pools:**
  - Higher initial supply (more collectible, broader accessibility)
  - Captures viral momentum and memorable moments
  - Rapid auction period: 1-3 hours

## Pool Creation Process

When content reaches the viral threshold, the following steps occur:
1. **Creator Notification:** Automatic eligibility notification sent to creator
2. **Manual Auction Start:** Creator initiates fair launch auction
3. **Community Participation:** Open bidding period with transparent pricing
4. **Pool Deployment:** Successful auction creates active trading pool
5. **Token Distribution:** Tokens distributed proportionally to all auction participants

## Liquidity Management

- **Reserve Accumulation:**
  - Buy transactions add MySo to pool reserves
  - Sell transactions remove MySo from pool reserves
  - Trading fees distributed before reserve updates
- **Automatic Balancing:**
  - Pool automatically maintains liquidity ratios
  - Quadratic pricing curve adjusts to supply changes
- **Continuous Trading:**
  - Always available liquidity (AMM guarantees trading availability)
  - Instant settlement, scalable for high volumes

## Security and Control Systems

- **Trading Halt Mechanisms:**
  - Authorized entities can halt/resume trading for specific pools in emergencies
  - Triggers: security incidents, technical issues, governance decisions, legal compliance
- **Block List Integration:**
  - Platform-wide and creator-level blocks
  - Bidirectional enforcement (mutual blocking prevents all interactions)
  - Real-time verification at transaction time
- **Anti-Manipulation Measures:**
  - 5% maximum hold per wallet (dynamic, adjusts as supply changes)
  - Self-trading prevention (creators cannot buy their own tokens)
  - All price movements reflect genuine external demand

## Performance Optimization

- Optimized data structures for O(1) lookups
- Minimal on-chain storage with maximum functionality
- Batch and parallel processing for high throughput
- Sub-second execution, thousands of concurrent trades supported

## Proof of Creativity Integration

When content is determined to be derivative, pools automatically configure revenue redirection to compensate original creators. Fee distribution is transparent and real-time, supporting both original and derivative creators.

## Pool Lifecycle Management

- Continuous trading, fee distribution, and security monitoring
- Parameters can be updated through governance
- Designed for long-term sustainability and adaptability as the platform evolves

## Strategic Pool Management

- **For Creators:**
  - Content quality, community engagement, and timing drive success
  - Multi-platform promotion increases pool visibility
- **For Token Holders:**
  - Assess creator potential, community strength, and pool maturity
  - Diversify across multiple creators and content types
  - Manage trading frequency and hold duration to optimize returns

Token Pool Management creates a robust, scalable, and secure foundation for Social Proof Token trading while maintaining the flexibility needed to adapt to the dynamic nature of social media content and community engagement.

_Emergency trading controls may be activated by governance in exceptional circumstances._
