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

The Proof of Creativity dispute system provides a **democratic, stake-based mechanism** for challenging PoC decisions. When post owners believe their content has been incorrectly classified, they can submit disputes that are resolved through community voting with economic incentives.

## Overview

The dispute system enables **community governance** over content authenticity decisions:

* **Post owners** can challenge PoC badges or revenue redirections
* **Community members** vote with MySo tokens at stake
* **Economic incentives** reward accurate voting and deter frivolous disputes
* **Democratic resolution** ensures fair outcomes through collective judgment

## When to Dispute

### Disputable PoC Decisions

Post owners can dispute when they believe:

1. **Incorrect Revenue Redirection**: Content marked as derivative when it's actually original
2. **Missing PoC Badge**: Original content that should have received a badge
3. **Wrong Original Creator**: Redirection going to incorrect creator
4. **Threshold Issues**: Content similarity assessment was inaccurate

### Who Can Dispute

**Only the post owner** can submit disputes for their content:

* Must be the wallet address that created the post
* Content must have existing PoC data (badge or redirection)
* Dispute requires economic stake to prevent spam

## Dispute Process

### 1. Dispute Submission

Post owners can submit disputes using `submit_poc_dispute` with evidence and required payment.

**Requirements:**

* **Dispute Cost**: 5 MySo paid by disputer
* **Protocol Fee**: 1 MySo additional fee to ecosystem treasury
* **Evidence**: Text description of dispute reasoning
* **Post Ownership**: Caller must own the disputed post

**Dispute Creation:**

* Unique dispute ID generated
* Voting period automatically scheduled (7 epochs)
* Dispute fee sent to ecosystem treasury
* Community voting opens next epoch

### 2. Community Voting Period

**Voting Duration**: 7 epochs from dispute submission**Voting Options**:

* **Uphold**: Keep original PoC decision (badge/redirection)
* **Overturn**: Remove PoC decision (clear badge/redirection)

**Stake Requirements**:

* **Minimum Stake**: 1 MySo per vote
* **Maximum Stake**: 100 MySo per vote
* **One Vote Per Address**: Each wallet can vote once per dispute

### 3. Voting Mechanism

Community members vote using `vote_on_dispute` with their chosen side and MySo stake amount.

**Voting Process:**

1. **Stake Validation**: Ensure stake amount within limits
2. **Timing Check**: Verify voting period is active
3. **Duplicate Prevention**: Ensure voter hasn't already voted
4. **Stake Collection**: MySo tokens held in dispute contract
5. **Vote Recording**: Vote choice and stake amount logged

### 4. Dispute Resolution

**Automatic Resolution**: After voting period ends using `resolve_dispute_voting`**Winning Determination**: Side with higher total stake wins**Economic Distribution**: Winners share rewards from losing side

**Resolution Outcomes:**

* **Uphold Wins**: Original PoC decision maintained
* **Overturn Wins**: PoC data cleared from post (badge removed or redirection eliminated)

## Economic Mechanics

### Dispute Costs

* **Entry Fee**: 5 MySo (prevents frivolous disputes)
* **Protocol Fee**: 1 MySo (supports ecosystem treasury)
* **Total Cost**: 6 MySo required to submit dispute
* **Non-Refundable**: Fees not returned regardless of outcome

### Voting Stakes

**Individual Limits:**

* Minimum: 1 MySo per vote
* Maximum: 100 MySo per vote
* **Proportional Influence**: Higher stakes have more voting weight

**Collective Dynamics:**

* **Total Uphold Stake**: Sum of all "uphold" votes
* **Total Overturn Stake**: Sum of all "overturn" votes
* **Winning Side**: Side with higher total stake

### Reward Distribution

**Winners Share Losers' Stakes:**

```
Individual Reward = (Individual Stake / Total Winning Stake) × Total Losing Stake
Total Payout = Individual Stake + Individual Reward
```

**Example Scenario:**

* **Total Uphold Stakes**: 100 MySo (winning side)
* **Total Overturn Stakes**: 60 MySo (losing side)
* **Individual Voter**: Staked 20 MySo on uphold
* **Reward Calculation**: (20/100) × 60 = 12 MySo bonus
* **Total Payout**: 20 MySo (original stake) + 12 MySo (reward) = 32 MySo

### Economic Incentives

**For Accurate Voters:**

* **Profit Opportunity**: Earn rewards from incorrect voters
* **Risk Management**: Only stake what you can afford to lose
* **Information Advantage**: Research content thoroughly before voting

**Against Frivolous Disputes:**

* **Entry Cost**: 6 MySo barrier discourages weak disputes
* **Community Scrutiny**: Poor disputes likely to lose
* **Reputation Risk**: Failed disputes may harm credibility

## Dispute Structure

### Technical Implementation

Each dispute contains comprehensive information including disputer details, voting period timing, accumulated stakes for each side, voter records, and reward pool for distribution.

## Dispute Lifecycle

### Phase 1: Submission (Immediate)

* Post owner identifies PoC issue
* Submits dispute with evidence and payment
* Dispute registered in system
* Next epoch voting period scheduled

### Phase 2: Voting (7 Epochs)

* Community members can vote with stakes
* Vote choices and amounts recorded
* Running totals maintained for each side
* New voters can join throughout period

### Phase 3: Resolution (Automatic)

* After voting period ends, resolution triggered
* Winning side determined by total stakes
* PoC decision either upheld or overturned
* Post data updated accordingly

### Phase 4: Reward Claims (Manual)

* Winning voters can claim rewards
* Proportional distribution based on stakes
* Losing stakes distributed to winners
* Dispute marked as finalized

## Integration with PoC System

### Badge Disputes

**Scenario**: Post owner believes their original content should have a PoC badge**If Overturn Wins**:

* Clear any existing redirection
* Issue PoC badge to the post
* Update token pool synchronization

### Redirection Disputes

**Scenario**: Post owner believes revenue redirection is incorrect**If Overturn Wins**:

* Remove revenue redirection rules
* Future revenue goes fully to post owner
* Historical redirections not reversed

### Token Pool Updates

**Automatic Synchronization**: Dispute resolutions trigger token pool updates**Consistent State**: Token trading respects updated PoC decisions**Real-time Application**: Changes apply immediately to future transactions

## Governance and Statistics

### Registry Tracking

The PoC Registry maintains comprehensive statistics about dispute activity, voting participation, and resolution outcomes.

### Available Analytics

* **Dispute Success Rate**: Percentage of disputes that overturn original decisions
* **Voting Participation**: Community engagement in dispute resolution
* **Economic Activity**: Total MySo staked in dispute voting
* **Resolution Time**: Average time from submission to resolution

### Community Health Metrics

* **Dispute Frequency**: Rate of disputes relative to content volume
* **Voter Accuracy**: Track performance of frequent voters
* **Content Quality**: Impact of disputes on overall content authenticity

## Best Practices

### For Disputers

* **Strong Evidence**: Provide clear reasoning for dispute
* **Cost Consideration**: Ensure potential benefit exceeds 6 MySo cost
* **Community Sentiment**: Gauge likely community response
* **Documentation**: Maintain records of original content creation

### For Voters

* **Due Diligence**: Research content and evidence thoroughly
* **Stake Management**: Only stake amounts you can afford to lose
* **Consistency**: Develop consistent voting principles
* **Information Gathering**: Consider all available evidence before voting

### For Platforms

* **Dispute Visibility**: Highlight active disputes to encourage participation
* **Evidence Display**: Provide clear interfaces for viewing dispute details
* **Voting Education**: Help users understand stake-based voting mechanics
* **Community Building**: Foster engaged, informed voting communities

The community dispute system creates a **self-regulating, economically incentivized** mechanism for resolving content authenticity questions while maintaining democratic governance and protecting against both frivolous disputes and incorrect PoC decisions.
