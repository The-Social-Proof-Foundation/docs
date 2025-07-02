---
icon: list-ol
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

### Central Limit Order Book (CLOB)
- **On-chain Order Matching**: All order matching happens directly on MySocial blockchain
- **Price-Time Priority**: Orders matched based on price first, then submission time
- **Order Types**: Market orders, limit orders, and other standard order types
- **Immediate Settlement**: Trades settle immediately on the blockchain

### Performance and Features
- **On-Chain Settlement**: Immediate trade finality with no intermediaries
- **Fee Payments**: All transaction fees paid in MySo tokens
- **Standard Order Management**: Full CLOB functionality with real-time order book updates

## Trading Pairs

### MySo/USDC - Primary Trading Pair

**Base Asset:** MySo (MySocial native token)  
**Quote Asset:** USDC (USD Coin)

This is currently the only supported trading pair on MySocial's order book, designed strategically to serve multiple critical functions:

**Trading Mechanics:**
- Users can trade MySo for USDC and vice versa
- All order book functionality (limit orders, market orders, etc.) operates on this pair
- Real-time price discovery establishes MySo's market value against USD

**Strategic Benefits:**
- **Price Discovery**: Establishes MySo's value against the US dollar
- **Bridge Gateway**: USDC serves as the primary bridge currency for cross-chain movement
- **Liquidity Focus**: Concentrating trading on one pair builds deeper liquidity pools
- **User Simplicity**: Clear, straightforward trading path for entering and exiting MySocial

## Bridge Integration

The order book functions as MySocial's primary bridge interface, with USDC serving as the gateway currency:

### Cross-Chain Asset Flow
1. **Entry**: Users bridge USDC from other chains (Ethereum, Polygon, etc.) to MySocial
2. **Exchange**: Bridged USDC can be immediately traded for MySo on the order book
3. **Exit**: MySo can be traded back to USDC, then bridged to other blockchains
4. **Accessibility**: Immediate trading availability after bridging operations

### Bridge Currency Role
USDC's role as the bridge currency provides:
- **Multi-Chain Support**: Compatible with USDC across multiple blockchain networks
- **Stability**: Dollar-pegged asset reduces volatility during cross-chain transfers
- **Liquidity**: Established USDC markets enable efficient value transfer
- **Integration**: Seamless connection between MySocial and broader DeFi ecosystem

## Economic Role

### MySo Token Utility
The order book creates essential utility for MySo tokens:
- **Primary Trading**: MySo/USDC provides the main trading functionality for the native token
- **Transaction Fees**: All order book operations require MySo for blockchain fees
- **Bridge Operations**: MySo needed for cross-chain transaction execution
- **Value Establishment**: Order book trading establishes MySo's market price

### Ecosystem Function
- **Gateway Role**: The order book serves as the primary entry and exit point for the MySocial ecosystem
- **Price Discovery**: Continuous trading establishes fair market value for MySo
- **Liquidity Provision**: Concentrated trading pairs build sustainable liquidity
- **Cross-Chain Bridge**: Essential infrastructure for multi-blockchain interoperability

The MySo/USDC order book provides the foundational trading and bridge infrastructure that enables MySocial's cross-chain ecosystem while establishing clear price discovery for the native token.
