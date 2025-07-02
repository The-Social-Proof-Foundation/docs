---
icon: percent
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

# Fee Distribution

The Social Proof Token fee distribution system ensures sustainable ecosystem economics while rewarding creators, platforms, and the broader community. This transparent, automated system distributes trading fees to support long-term platform growth and creator incentives.

{% hint style="info" %}
Note: The fee structure is subject to change based on a DAO majority vote.
{% endhint %}

## Fee Structure Overview

All Social Proof Token trades (buy and sell) incur a **1.5% total fee** calculated on the trade value. This fee is automatically collected and distributed according to a predetermined allocation model.

| Recipient  | Standard Distribution | PoC Redirection (Example: 70% to original creator) |
|------------|----------------------|----------------------------------------------------|
| Creator    | 1.0%                 | 0.3% (derivative) / 0.7% (original)                |
| Platform   | 0.25%                | 0.25%                                              |
| Treasury   | 0.25%                | 0.25%                                              |

- **Standard Distribution:**
  - Creator: 1.0% (66.7% of total fees)
  - Platform: 0.25% (16.7% of total fees)
  - Treasury: 0.25% (16.7% of total fees)
- **PoC Integration:**
  - When PoC revenue redirection is active, the creator fee is split between the derivative and original creator based on the PoC redirection percentage.

## Technical Implementation

- Fees are collected and distributed in real time, with all transactions recorded on-chain for transparency.
- PoC integration ensures original creators are compensated for derivative content, and all distributions are paid in MySo tokens.

## Revenue Scenarios

**Example: $100 MySo Trade**
- Total Fee: $1.50 (1.5%)
- Creator Receives: $1.00 (1.0%)
- Platform Receives: $0.25 (0.25%)
- Treasury Receives: $0.25 (0.25%)
- Net Trade Amount: $98.50

**Example: $100 MySo Trade with 70% PoC Redirection**
- Total Fee: $1.50 (1.5%)
- Original Creator Receives: $0.70 (70% of 1.0%)
- Derivative Creator Receives: $0.30 (30% of 1.0%)
- Platform Receives: $0.25 (0.25%)
- Treasury Receives: $0.25 (0.25%)
- Net Trade Amount: $98.50

**High-Volume Creator Revenue Example:**
- Daily Creator Fees: 10 MySo (1.0% of 1,000 MySo daily trading volume)
- Monthly Creator Fees: 300 MySo (30 days)
- Annual Creator Fees: 3,650 MySo (365 days)

## Fee Governance

All fee parameters can be adjusted through governance, allowing the community to optimize the balance between creator incentives, platform sustainability, and ecosystem growth. Performance is monitored to ensure fees support long-term value for all stakeholders.

## Economic Implications

The fee distribution system creates a self-sustaining ecosystem where trading activity generates revenue for creators, platforms, and the community, driving continued growth and engagement.

_Emergency trading controls may be activated by governance in exceptional circumstances._
