---
icon: chart-candlestick
'---layout':
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

MySocial’s core order matching engine runs entirely on-chain, ensuring transparency, verifiability, and decentralization. The CLOB maintains an active list of buy and sell limit orders, matching them based on price-time priority. This guarantees efficient price discovery while ensuring minimal slippage for large orders.

Orders submitted to the MySocial order book are executed based on the following logic:

1. Limit orders are matched if a counterparty order exists at the requested price.
2. If no match exists, the order remains on the book, waiting for execution.
3. If a market order is placed, it will execute against existing orders at the best available price.

### AMM Liquidity Pool as a Fallback

To maintain continuous liquidity, MySocial incorporates an AMM fallback mechanism that interacts with liquidity pools. If an order remains unmatched on the CLOB due to a lack of liquidity at a specific price level, the system routes the remainder of the order to AMM pools to provide instant execution.

This method ensures that:

* Traders receive the best possible price using order book matching first.
* Unmatched portions of market orders are executed against an AMM pool when necessary.
* Liquidity providers (LPs) earn fees by supplying assets to AMM pools, supporting deeper liquidity.

### Security and Finality

Unlike traditional exchanges that rely on external sequencers or off-chain computation, MySocial executes all trades on-chain, ensuring full transparency and verifiability. The system does not rely on custodial intermediaries, meaning users maintain full control of their assets throughout the trade lifecycle.

Additionally, MySocial:

* Guarantees trade finality on-chain through deterministic execution.
* Prevents transaction frontrunning by utilizing fair transaction ordering.
* Uses the native MYSO token for transaction fees, eliminating the need for external utility tokens.

### Scalability & Performance

The MySocial trading protocol is designed to scale with increasing demand. The order book can process thousands of transactions per second, ensuring rapid order execution even during peak market activity. AMM integration further enhances liquidity, making the platform well-suited for high-volume trading driven by social media interactions.

## Conclusion

MySocial’s trading engine is not a traditional standalone CLOB or AMM but a hybrid system that optimizes both approaches. By prioritizing order book execution first and falling back to AMMs when necessary, we ensure both efficiency and continuous liquidity. This innovation allows MySocial to support a high-speed, low-cost, decentralized trading experience, perfectly aligned with the needs of a social media-based blockchain ecosystem.
