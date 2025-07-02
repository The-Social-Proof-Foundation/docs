---
icon: chart-candlestick
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

# Order Book

MySocial's order book provides Central Limit Order Book (CLOB) functionality for trading MySo against USDC, serving as the primary gateway for cross-chain asset movement and price discovery.

## Core Functionality

The order book operates entirely on-chain, matching orders based on price and submission time. Supported order types include:
- Market orders
- Limit orders
- Other standard order types

**Trading Mechanics:**
- Price-time priority: orders matched based on price first, then submission time
- Immediate settlement: trades settle instantly on the blockchain
- Real-time updates: full CLOB functionality
- All transaction fees paid in MySo tokens

## Trading Pairs

Currently, the primary trading pair is MySo/USDC:
- **Base Asset:** MySo (MySocial native token)
- **Quote Asset:** USDC (USD Coin)

This pair is central to the ecosystem, enabling users to trade MySo for USDC and vice versa. Real-time price discovery establishes MySo's market value, and the focus on a single pair builds deep liquidity and simplifies the trading experience.

## Bridge Integration

The order book acts as the main bridge interface for MySocial, with USDC serving as the gateway currency. Cross-chain asset flow works as follows:
1. **Entry:** Users bridge USDC from other chains (Ethereum, Polygon, etc.) to MySocial
2. **Exchange:** Bridged USDC can be immediately traded for MySo on the order book
3. **Exit:** MySo can be traded back to USDC, then bridged to other blockchains
4. **Accessibility:** Immediate trading availability after bridging operations

**Bridge Currency Role:**
- Multi-chain support: compatible with USDC across multiple blockchain networks
- Stability: dollar-pegged asset reduces volatility during cross-chain transfers
- Liquidity: established USDC markets enable efficient value transfer
- Integration: seamless connection between MySocial and broader DeFi ecosystem

## Economic Role

The order book is essential for establishing MySo's utility and value:
- Primary trading: MySo/USDC provides the main trading functionality for the native token
- Transaction fees: all order book operations require MySo for blockchain fees
- Bridge operations: MySo needed for cross-chain transaction execution
- Value establishment: order book trading establishes MySo's market price

## Ecosystem Function

As the primary entry and exit point, the order book underpins MySocial's cross-chain ecosystem. It enables price discovery, liquidity provision, and interoperability with other blockchains, supporting the growth and stability of the platform.

The MySo/USDC order book provides the foundational trading and bridge infrastructure that enables MySocial's cross-chain ecosystem while establishing clear price discovery for the native token.
