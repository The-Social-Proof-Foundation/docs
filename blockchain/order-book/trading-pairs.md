---
icon: arrows-left-right
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

# Trading Pairs

MySocial's order book currently supports trading between MySo (the native token) and USDC, serving as the foundation for cross-chain asset movement and price discovery.

## Current Trading Pair

### MySo/USDC
**Base Asset:** MySo (MySocial native token)  
**Quote Asset:** USDC (USD Coin)

This is the primary and currently only supported trading pair on MySocial's order book.

**Key Facts:**
- Users can trade MySo for USDC and vice versa
- USDC comes from bridged assets from other blockchains
- This pair serves as the main way to exchange MySo for a stable dollar-pegged asset
- All order book functionality (limit orders, market orders, etc.) works with this pair

## Bridge Integration

USDC serves as the bridge currency:
- Users bridge USDC from other chains (Ethereum, Polygon, etc.) to MySocial
- They can then trade that USDC for MySo on the order book
- To exit, users trade MySo for USDC, then bridge USDC back to other chains
- This makes the order book the gateway for moving value in and out of MySocial

## Why This Pair

- **Price Discovery**: Establishes MySo's value against USD
- **Bridge Gateway**: USDC is the main bridge currency
- **Liquidity Focus**: Concentrating on one pair builds deeper liquidity
- **Simplicity**: Clear trading path for users entering/exiting MySocial

The MySo/USDC pair provides the essential trading and bridge functionality for the MySocial ecosystem. 