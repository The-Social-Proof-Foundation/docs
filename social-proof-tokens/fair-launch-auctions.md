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

# Fair Launch Auctions

Fair Launch Auctions ensure equitable distribution of Social Proof Tokens when content or creators reach viral thresholds. This system prevents insider advantages and gives the entire community equal opportunity to participate in token launches.

## How Fair Launch Auctions Work

### Auction Initiation Process
1. **Viral Threshold Achievement**: Content reaches the required viral score
2. **Creator Notification**: Owner receives eligibility notification  
3. **Manual Auction Start**: Creator must manually initiate the auction on their behalf
4. **Community Participation**: Open bidding period begins
5. **Fair Distribution**: Tokens allocated proportionally to contributions

### Auction Duration Differences

**Post Token Auctions:**
- **Duration**: 1-3 hours (creator can choose within this range)
- **Rationale**: Posts are time-sensitive, shorter auctions capture immediate viral momentum
- **Flexibility**: Creator chooses specific duration based on content type and strategy

**Profile Token Auctions:**
- **Duration**: 1-3 days (creator can choose within this range)  
- **Rationale**: Profiles represent long-term value, longer auctions allow thorough price discovery
- **Community Building**: Extended period enables broader community participation

**Governance Adjustability:**
All auction duration limits can be modified through governance mechanisms to adapt to ecosystem needs and market conditions.

## Technical Implementation

### Auction Structure
Each auction tracks essential information including participant contributions, timing, and token distribution details.

### Auction Lifecycle

**Status Progression:**
- **Pending (0)**: Auction created but not yet started
- **Active (1)**: Currently accepting contributions
- **Ended (2)**: Time expired, no longer accepting bids
- **Finalized (3)**: Tokens distributed, trading active

### Contribution Mechanism
**Contribution Process:**
1. **Validation**: Verify auction is active and amount is sufficient
2. **Payment Collection**: MySo tokens transferred to auction pool
3. **Record Keeping**: Contributor and amount recorded
4. **Running Totals**: Total contribution amount updated
5. **Event Emission**: Contribution event broadcasted

## Token Supply Calculation

### Dynamic Scaling Algorithm
The system uses sophisticated mathematical formulas to determine initial token supply based on total auction contributions:

**Mathematical Formula:**
```
sqrt_contribution = √(total_contribution)
cbrt_contribution = ∛(sqrt_contribution)  // Approximated as √(√(contribution))
scale_factor = sqrt_contribution × cbrt_contribution  // contribution^0.75
scale_factor = scale_factor ÷ 1000  // Make tokens premium assets
```

**Token Type Multipliers:**
- **Profile Tokens**: 1x multiplier (lower supply, higher individual value)
- **Post Tokens**: 10x multiplier (higher supply, more collectible nature)

**Supply Calculation:**
```
initial_token_supply = if (profile_token) {
    scale_factor × 1     // Premium profile tokens
} else {
    scale_factor × 10    // Collectible post tokens
}

// Minimum guarantee
if (initial_token_supply == 0) {
    initial_token_supply = 1
}
```

### Supply Rationale
**Non-Linear Scaling Benefits:**
- **Anti-Front-Running**: Larger pools get proportionally more tokens, reducing first-mover advantages
- **AMM Efficiency**: Proper token supply prevents extreme price volatility
- **Fair Valuation**: Balances token scarcity with market liquidity needs
- **Premium Asset Status**: Ensures tokens are worth more than base MySo currency

## Fair Distribution Process

### Proportional Allocation
All participants receive tokens based on their percentage contribution to the total auction pool:

```
participant_tokens = (participant_contribution ÷ total_contribution) × total_token_supply
```

**Example Allocation:**
- **Total Contributions**: 1,000 MySo
- **Total Tokens**: 10,000 tokens
- **Alice's Contribution**: 100 MySo (10%)
- **Alice's Allocation**: 1,000 tokens (10% of supply)

### Distribution Implementation
After auction completion, tokens are automatically distributed to all participants based on their proportional contribution to the total pool.

## Security and Anti-Gaming Features

### Block List Integration
The auction system includes comprehensive block list protections:

**Bidding Restrictions:**
- Blocked users cannot participate in auctions
- Creators cannot start auctions if they're blocked by the platform
- Block list status checked at contribution time, not just auction start

**Multi-Level Protection:**
- **Platform-Level Blocks**: Platform operators can block malicious users
- **Creator-Level Blocks**: Creators can block specific users from their auctions
- **Community Standards**: Maintains quality and safety for all participants

**Implementation Details:**
Block list status is verified in real-time before allowing any auction participation.

### Anti-Manipulation Measures
**Equal Opportunity:**
- No insider information or pre-sales
- All participants bid during the same time window
- Transparent contribution tracking and final allocation

**Contribution Validation:**
- Minimum and maximum contribution limits prevent gaming
- Real MySo tokens required (no fake contributions possible)
- All transactions recorded on-chain for transparency

## Auction Economics

### Price Discovery Mechanism
**Initial Token Price Calculation:**
```
initial_token_price = total_contribution ÷ total_tokens_issued
```

This creates market-driven price discovery where:
- Higher community interest → Higher contribution → Higher initial price
- Token value reflects genuine community demand
- No arbitrary pricing by creators or platforms

### Fee Structure
**Auction Fees:**
- **No Auction Fees**: Participants pay no additional fees to participate
- **Trading Fees Apply Later**: Standard 1.5% trading fees apply once AMM trading begins
- **Gas Costs Only**: Participants only pay blockchain transaction costs

### Auction Failure Handling
**Minimum Participation:**
- Auctions require at least one contribution to proceed
- Failed auctions (no contributions) do not create token pools
- Contributors can withdraw if auction fails to finalize

## Strategic Considerations

### For Creators
**Auction Timing:**
- Launch auctions when community engagement is highest
- Consider time zones and platform activity patterns
- Use viral momentum to maximize participation

**Duration Selection:**
- **Shorter Auctions (Posts)**: Capture immediate viral attention
- **Longer Auctions (Profiles)**: Allow broader community discovery and participation
- **Balance**: Quick enough to maintain interest, long enough for fair participation

### For Participants
**Bidding Strategy:**
- Early contributions don't provide advantages in token allocation
- Contribution size determines final token percentage
- Assess creator/content value before committing MySo tokens

**Risk Assessment:**
- Evaluate creator's long-term potential and engagement history
- Consider post virality sustainability and lasting appeal
- Understand that initial auction price becomes baseline for AMM trading

### For Platforms
**Ecosystem Health:**
- Fair auctions build trust and encourage participation
- Quality token launches enhance platform reputation
- Transparent process reduces disputes and complaints

**Community Growth:**
- Democratic participation encourages broader ecosystem engagement
- Success stories attract new users and creators
- Fair distribution prevents wealth concentration

The Fair Launch Auction system ensures **democratic access** to Social Proof Token investments while creating genuine price discovery and preventing manipulation, fostering a healthy ecosystem where community value determines token success.

*Emergency trading controls may be activated by governance in exceptional circumstances.* 