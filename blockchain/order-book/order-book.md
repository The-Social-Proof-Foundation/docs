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

# Overview

MySocial's order book provides Central Limit Order Book (CLOB) functionality for trading MySo against USDC, serving as the primary gateway for cross-chain asset movement.

## Core Functionality

### Central Limit Order Book (CLOB)
- **On-chain Order Matching**: All order matching happens directly on MySocial blockchain
- **Price-Time Priority**: Orders matched based on price first, then submission time
- **Order Types**: Market orders, limit orders, and other standard order types
- **Immediate Settlement**: Trades settle immediately on the blockchain

### Primary Trading Pair
**MySo/USDC**
- MySo (MySocial native token) trades against USDC
- USDC comes from bridged assets from other blockchains
- This is currently the only supported trading pair

## Bridge Integration

### Gateway Function
The order book serves as MySocial's bridge interface:
- **Asset Entry**: USDC bridged from other chains can be traded for MySo
- **Asset Exit**: MySo can be traded for USDC, then bridged back to other chains
- **Trading Access**: Immediate trading availability after bridging

### Bridge Currency
USDC serves as the primary bridge currency from multiple blockchains.

## Technical Features

### Order Management
Standard CLOB order management with on-chain execution and immediate settlement.

### Performance
- **On-Chain Settlement**: Immediate trade finality
- **Fee Payments**: Transaction fees paid in MySo

## Economic Role

### MySo Token Utility
- **Primary Trading**: MySo/USDC provides main trading functionality
- **Transaction Fees**: All order book operations use MySo for fees
- **Bridge Operations**: MySo required for cross-chain functionality

### Price Discovery
The order book establishes MySo's value against USD through the USDC trading pair.
