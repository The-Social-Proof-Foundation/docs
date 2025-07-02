---
icon: gavel
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

# Community Dispute System

The Proof of Creativity dispute system provides a democratic, stake-based mechanism for challenging PoC decisions. When post owners believe their content has been incorrectly classified, they can submit disputes that are resolved through community voting with economic incentives.

## Overview

The dispute system enables community governance over content authenticity decisions. Post owners can challenge PoC badges or revenue redirections, and community members vote with MySo tokens at stake. Economic incentives reward accurate voting and deter frivolous disputes, ensuring fair outcomes through collective judgment.

## When to Dispute

Post owners can dispute PoC decisions if they believe there is an incorrect revenue redirection, a missing PoC badge, a wrong original creator, or a threshold issue. Only the post owner can submit disputes, and a dispute requires an economic stake to prevent spam.

## Dispute Process

Disputes are submitted using `submit_poc_dispute` with evidence and a payment of 5 MySo plus a 1 MySo protocol fee. Each dispute is assigned a unique ID, and a 7-epoch voting period is scheduled. Community members can vote to uphold or overturn the PoC decision, staking between 1 and 100 MySo per vote. Each wallet can vote once per dispute.

After the voting period, the side with the higher total stake wins. Winners share rewards from the losing side, calculated as:

```
Individual Reward = (Individual Stake / Total Winning Stake) × Total Losing Stake
Total Payout = Individual Stake + Individual Reward
```

For example, if the total uphold stake is 100 MySo and the total overturn stake is 60 MySo, a voter who staked 20 MySo on uphold would receive a 12 MySo bonus, for a total payout of 32 MySo.

## Dispute Lifecycle

Disputes progress through submission, voting, resolution, and reward claim phases. After submission, voting lasts 7 epochs. Once resolved, the winning side can claim rewards, and the dispute is finalized.

## Integration with PoC System

Badge disputes can result in badge issuance if overturned, while redirection disputes can remove revenue rules for future earnings. Token pools are automatically updated to reflect dispute outcomes.

## Governance and Statistics

The PoC Registry tracks dispute activity, voting participation, and resolution outcomes, providing analytics on dispute success rates, voting participation, economic activity, and resolution times.

The community dispute system creates a self-regulating, economically incentivized mechanism for resolving content authenticity questions while maintaining democratic governance and protecting against both frivolous disputes and incorrect PoC decisions.
