---
icon: link
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

# Social Proof Token Integration

The Proof of Creativity system seamlessly integrates with MySocial's **Social Proof Tokens**, ensuring that token economics reflect content authenticity and original creators receive fair compensation from token trading activities.

## Integration Overview

PoC decisions automatically impact Social Proof Token pools:

- **PoC Badges**: Enhance token pool value and market confidence
- **Revenue Redirection**: Applies to all token trading fees and revenue
- **Real-time Sync**: Token pools immediately reflect PoC status changes
- **Market Transparency**: Traders know the true revenue distribution

## How Token Pools Work

### Token Pool Structure
Each token pool contains PoC revenue redirection data that determines how trading fees are distributed between current and original creators.

### PoC Data Synchronization
Token pools automatically synchronize with their associated posts using `update_token_poc_data`, ensuring consistent revenue distribution rules.

## Revenue Distribution in Token Trading

### Creator Fee Distribution
When users trade Social Proof Tokens, **1% creator fees** are automatically subject to PoC redirection through `distribute_creator_fee_from_pool`, which splits payments between original and current creators based on redirection percentages.

### Trading Fee Breakdown
For every token trade, fees are distributed as:
- **1.0% Creator Fee**: Subject to PoC redirection
- **0.25% Platform Fee**: Goes to platform treasury  
- **0.25% Ecosystem Fee**: Goes to ecosystem treasury

**Example with PoC Redirection:**
- Trade Value: 1000 MYS
- Creator Fee: 10 MYS
- PoC Redirection: 60% (6 MYS to original creator)
- Post Owner Receives: 4 MYS (40% remainder)

## Market Impact of PoC Status

### Badge Holder Advantages
**Original Content (PoC Badge)**:
- **Full Revenue**: 100% of creator fees go to post owner
- **Market Confidence**: Clear authenticity signal for investors
- **Premium Valuation**: Original content commands higher prices
- **Reduced Risk**: No revenue redirection uncertainty

### Derivative Content Considerations
**Derivative Content (Revenue Redirection)**:
- **Shared Revenue**: Portion of creator fees redirected to original creator
- **Market Disclosure**: Redirection percentage visible to all traders
- **Value Adjustment**: Token prices typically reflect revenue sharing
- **Transparency**: Clear understanding of fee distribution

## Automatic Synchronization

### Event-Driven Updates
When PoC analysis completes, the system automatically triggers token pool synchronization by emitting `TokenPoolSyncNeededEvent` events.

### Sync Process
1. **PoC Analysis Completes**: Oracle determines badge or redirection
2. **Post Updated**: PoC data stored in post object
3. **Event Emitted**: System signals need for token pool update
4. **Pool Synchronization**: Token pool PoC data updated to match post
5. **Market Notification**: Traders informed of PoC status changes

## Token Pool Creation

### Post Token Requirements
For a post to have an associated token pool, it must:
- **Viral Threshold**: Reach 100+ viral points (likes×1 + comments×3 + tips×10)
- **Community Interest**: Demonstrate sufficient engagement
- **Market Demand**: Users must want to trade tokens for this content

### Pre-Launch Auctions
**Auction Process**:
1. **Viral Post**: Content reaches viral threshold
2. **Auction Launch**: 1-3 hour auction period for posts
3. **Community Bidding**: Users contribute MYS for token allocation
4. **Pool Creation**: Auction finalizes and creates token pool
5. **PoC Integration**: Existing PoC data automatically applied to pool

### Post-Auction PoC Updates
If PoC status changes after token pool creation:
- **Dispute Resolution**: Community disputes can alter PoC status
- **Automatic Updates**: Token pools immediately reflect changes
- **Trading Continuity**: Trading continues with updated revenue distribution

## Economic Examples

### Original Content Token Trading
**Scenario**: Alice's original art (PoC badge) reaches viral threshold
- **Token Pool Created**: 10,000 tokens distributed via auction
- **User Buys**: Bob purchases 100 tokens for 500 MYS
- **Creator Fee**: 5 MYS (1% of trade value)
- **PoC Status**: No redirection (original content)
- **Result**: Alice receives full 5 MYS creator fee

### Derivative Content Token Trading  
**Scenario**: Carol's derivative art (60% redirection to Alice) has token pool
- **User Sells**: David sells 50 tokens for 300 MYS
- **Creator Fee**: 3 MYS (1% of trade value)
- **PoC Redirection**: 60% to Alice, 40% to Carol
- **Result**: Alice receives 1.8 MYS, Carol receives 1.2 MYS

### Complex Trading Chain
**Scenario**: Multiple levels of derivative content
- **Original**: Alice (PoC badge)
- **Derivative 1**: Bob (75% redirection to Alice)
- **Derivative 2**: Carol reposts Bob's content
- **Trading**: Users trade tokens for Carol's repost
- **Revenue Flow**: Trading fees split between platform, then post owner (Bob), then PoC redirection (Alice)

## Market Transparency Features

### Pool Information Display
Token pools provide complete PoC information through functions like `get_poc_redirect_to`, `get_poc_redirect_percentage`, and `has_poc_redirection`.

### Trading Interface Benefits
- **Clear Disclosure**: Revenue redirection percentages prominently displayed
- **Creator Attribution**: Original creator addresses shown for derivative content
- **Revenue Preview**: Traders can see exactly how fees will be distributed
- **Historical Data**: Track creator earnings from both original and derivative content

## Risk and Compliance

### For Token Traders
**Due Diligence Factors**:
- **PoC Status**: Check if content is original or derivative
- **Redirection Percentage**: Understand revenue sharing arrangements
- **Creator History**: Research both current and original creators
- **Dispute Risk**: Consider potential for PoC disputes affecting revenue

### For Content Creators
**Earnings Optimization**:
- **Original Content**: Maximize earnings by creating truly original work
- **PoC Badge Value**: Badges increase token pool attractiveness
- **Market Positioning**: Use PoC status as marketing advantage
- **Long-term Revenue**: Original creators benefit from all derivative uses

### For Platforms
**Compliance Benefits**:
- **Transparent Attribution**: Clear creator compensation records
- **Legal Framework**: On-chain evidence of revenue sharing
- **Dispute Resolution**: Established process for handling conflicts
- **Creator Retention**: Fair compensation encourages continued participation

## Integration with Dispute System

### Dispute Impact on Token Trading
When PoC disputes are submitted:
- **Trading Continues**: Token markets remain active during disputes
- **Revenue Uncertainty**: Some traders may adjust positions during voting
- **Resolution Impact**: Dispute outcomes immediately affect future fee distribution

### Post-Dispute Adjustments
If disputes change PoC status:
- **Immediate Updates**: Token pools sync with new PoC decisions
- **Market Adjustment**: Prices typically adjust to reflect new revenue structures
- **Historical Preservation**: Past fee distributions are not reversed
- **Future Clarity**: Clear revenue distribution going forward

## Ecosystem Benefits

### For the Creator Economy
- **Fair Compensation**: Original creators earn from derivative uses
- **Innovation Incentive**: Rewards original creativity over copying
- **Passive Income**: Ongoing earnings from successful content
- **Market Recognition**: PoC badges signal authenticity and value

### For Token Markets
- **Informed Trading**: Complete transparency about revenue flows
- **Risk Assessment**: Clear understanding of earning potential
- **Quality Signal**: PoC badges indicate authentic, original content
- **Market Efficiency**: Accurate pricing based on true revenue distribution

### For Platform Ecosystem
- **Legal Compliance**: Automated creator attribution and compensation
- **Reduced Disputes**: Clear revenue sharing reduces conflicts
- **Creator Retention**: Fair compensation encourages quality content
- **Market Growth**: Transparent, fair markets attract more participants

The integration between Proof of Creativity and Social Proof Tokens creates a **transparent, fair, and economically efficient** system that protects creator rights while enabling vibrant token markets based on authentic content value. 