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

# Fair Token Launches

Fair Token Launches ensure equitable distribution of Social Proof Tokens when content or creators reach viral thresholds. This system is designed to prevent insider advantages and give the entire community equal opportunity to participate in token launches.

## How Fair Token Launches Work

When content reaches the required viral score:

1. **Viral Threshold Achievement:** Content reaches the required viral score.
2. **Creator Notification:** Owner receives eligibility notification.
3. **Manual Auction Start:** Creator must manually initiate the auction.
4. **Community Participation:** Open bidding period begins.
5. **Fair Distribution:** Tokens allocated proportionally to contributions.

**Auction Duration:**
- **Post Token Auctions:** 1-3 hours (creator chooses duration)
- **Profile Token Auctions:** 1-3 days (creator chooses duration)
- All durations are adjustable by governance.

The auction lifecycle progresses through these status stages:
- **Pending:** Auction created but not yet started
- **Active:** Currently accepting contributions
- **Ended:** Time expired, no longer accepting bids
- **Finalized:** Tokens distributed, trading active

## Token Supply Calculation

Initial token supply is determined by a dynamic scaling algorithm:

```
sqrt_contribution = √(total_contribution)
cbrt_contribution = ∛(sqrt_contribution)  // Approximated as √(√(contribution))
scale_factor = sqrt_contribution × cbrt_contribution  // contribution^0.75
scale_factor = scale_factor ÷ 1000  // Make tokens premium assets
```

**Token Type Multipliers:**
- **Profile Tokens:** 1x multiplier (lower supply, higher value)
- **Post Tokens:** 10x multiplier (higher supply, more collectible)

**Supply Calculation:**
```
initial_token_supply = if (profile_token) {
    scale_factor × 1
} else {
    scale_factor × 10
}
if (initial_token_supply == 0) {
    initial_token_supply = 1
}
```

## Fair Distribution Process

- Tokens are distributed proportionally to each participant's contribution:
  - `participant_tokens = (participant_contribution ÷ total_contribution) × total_token_supply`
- After the auction, tokens are automatically allocated based on the share of the total pool.

## Security and Anti-Gaming Features

- **Block List Integration:**
  - Blocked users cannot participate in auctions.
  - Creators cannot start auctions if they're blocked by the platform.
  - Block list status checked at contribution time.
- **Anti-Manipulation:**
  - No insider information or pre-sales.
  - All participants bid during the same time window.
  - Minimum and maximum contribution limits prevent gaming.
  - All transactions recorded on-chain for transparency.

## Auction Economics

- **Initial Token Price Calculation:**
  - `initial_token_price = total_contribution ÷ total_tokens_issued`
- **Fees:**
  - No auction fees; only standard 1.5% trading fees apply once AMM trading begins.
  - Participants only pay blockchain transaction costs during the auction.
- **Auction Failure:**
  - Auctions require at least one contribution to proceed.
  - Failed auctions (no contributions) do not create token pools.
  - Contributors can withdraw if auction fails to finalize.

## Strategic Considerations

- **For Creators:**
  - Launch auctions when community engagement is highest.
  - Use viral momentum to maximize participation.
  - Choose auction duration based on content type and strategy.
- **For Participants:**
  - Early contributions do not provide allocation advantage.
  - Contribution size determines final token percentage.
  - Assess creator/content value before committing MySo tokens.
- **For Platforms:**
  - Fair auctions build trust and encourage participation.
  - Quality token launches enhance platform reputation.
  - Transparent process reduces disputes and complaints.

The Fair Launch Auction system ensures **democratic access** to Social Proof Token investments while creating genuine price discovery and preventing manipulation, fostering a healthy ecosystem where community value determines token success.

*Emergency trading controls may be activated by governance in exceptional circumstances.* 