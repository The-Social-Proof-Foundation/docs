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
