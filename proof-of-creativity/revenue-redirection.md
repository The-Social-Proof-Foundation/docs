---
icon: route
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

# Revenue Redirection System

The Proof of Creativity revenue redirection system ensures that **original creators receive fair compensation** when their content is used as the basis for derivative works. This automatic system protects creator rights while allowing derivative content to exist and generate revenue.

## How Revenue Redirection Works

When the oracle detects that content is **derivative** (similarity above threshold), the system automatically redirects a portion of all future revenue from that content to the original creator.

### Automatic Detection Process

1. **Similarity Analysis**: Oracle determines content similarity score
2. **Threshold Comparison**: Score compared against 95% similarity threshold
3. **Original Creator Identification**: System identifies the original content creator
4. **Redirection Calculation**: Percentage calculated based on similarity score
5. **Post Update**: Revenue redirection rules applied to all future monetization

### Redirection Formula

The system uses a **dynamic scaling formula** to determine redirection percentage:

```
Delta = (Similarity Score - Threshold) / (100 - Threshold)
Redirect Percentage = (Base Redirect % × Delta) / 100
```

**Example Calculations:**

| Similarity Score | Threshold | Delta | Final Redirect % |
|------------------|-----------|-------|------------------|
| 96% | 95% | 20% | 20% |
| 98% | 95% | 60% | 60% |
| 99% | 95% | 80% | 80% |
| 100% | 95% | 100% | 100% |

This ensures **proportional compensation** - higher similarity results in higher redirection.

## Technical Implementation

### Smart Contract Structure

Each post contains revenue redirection settings that specify the target address and percentage for redirecting earnings to original creators.

### Redirection Application

The system applies revenue redirection to **all monetization sources**:

#### Direct Tips to Posts
When users tip posts using `tip_post`, the system automatically applies PoC redirection through `apply_poc_redirection_and_transfer`.

#### Social Proof Token Sales
Revenue redirection is automatically applied to creator fees from token trading through `distribute_creator_fee_from_pool` and `apply_token_poc_redirection`.

#### Comment and Repost Tips
The system handles **complex tip scenarios**:

- **Comment Tips**: 80% to commenter, 20% to post owner (with PoC redirection on post owner's share)
- **Repost Tips**: 50% to reposter, 50% to original post (with PoC redirection applied to both if applicable)

## Revenue Split Examples

### Basic Tip Scenario
**Original Content**: Alice creates original artwork (PoC badge issued)
**Derivative Content**: Bob posts 98% similar content (60% redirection to Alice)
**Tip**: Carol tips Bob's post 100 MySo

**Result:**
- Alice receives: 60 MySo (redirected portion)
- Bob receives: 40 MySo (remaining portion)

### Social Proof Token Scenario
**Token Trading**: Users buy/sell tokens for Bob's derivative content
**Creator Fee**: 1% of trading volume goes to "creator"
**PoC Redirection**: 60% of creator fees redirected to Alice

**Example Trade**: 1000 MySo token purchase generates 10 MySo creator fee
- Alice receives: 6 MySo (60% redirection)
- Bob receives: 4 MySo (40% remainder)

### Complex Repost Scenario
**Chain of Content**: Alice (original) → Bob (derivative, 60% redirect) → Carol (reposts Bob's content)
**Tip**: David tips Carol's repost 100 MySo

**Revenue Split:**
1. **Repost Split**: 50 MySo to Carol, 50 MySo to Bob's original post
2. **PoC Redirection on Bob's share**: 30 MySo to Alice, 20 MySo to Bob
3. **Final Result**: Carol: 50 MySo, Alice: 30 MySo, Bob: 20 MySo

## Token Pool Integration

### Automatic Synchronization
Revenue redirection automatically applies to Social Proof Token pools through `update_token_poc_data`, which copies PoC settings from posts to their associated token pools.

### Real-time Updates
- **Post Analysis**: When PoC analysis completes, token pools are notified
- **Sync Events**: Events emitted to trigger automatic pool synchronization  
- **Consistent Rules**: Token trading and post monetization use identical redirection rules

## Economic Impact

### For Original Creators
- **Passive Income**: Receive compensation without active enforcement
- **Proportional Rewards**: Higher similarity = higher compensation
- **Broad Coverage**: Applies to all revenue streams from derivative content
- **No Action Required**: Automatic detection and redirection

### For Derivative Content Creators
- **Fair Use**: Can still create derivative content and earn revenue
- **Transparency**: Clear knowledge of redirection rules upfront
- **Residual Income**: Retain portion of revenue based on originality added
- **Legal Clarity**: On-chain evidence of compensation to original creator

### For the Ecosystem
- **Innovation Incentive**: Rewards original creativity over copying
- **Legal Framework**: Provides clear compensation mechanism
- **Reduced Disputes**: Automatic resolution of many ownership conflicts
- **Creator Retention**: Encourages continued content creation

## Administrative Features

### Configuration Management
The PoC configuration system manages redirect percentages and similarity thresholds for different media types, all adjustable through governance.

### Governance Controls
- **Threshold Adjustment**: Community can modify similarity thresholds
- **Base Percentage**: Default redirection percentage can be updated
- **Media-Specific Rules**: Different rules for images, videos, audio
- **Emergency Controls**: Admin override capabilities for system issues

## Monitoring and Analytics

### Revenue Tracking
The system provides comprehensive analytics through the PoC Registry, tracking redirections created, disputes submitted, and voting activity.

### Available Metrics
- **Redirection Volume**: Total MySo redirected to original creators
- **Content Analysis**: Percentage of content requiring redirection
- **Creator Benefits**: Individual creator earnings from redirections
- **Platform Health**: Impact on content quality and creator retention

## Integration with Dispute System

### Challenge Mechanism
Revenue redirections can be disputed through the community system:

- **Post Owner Rights**: Derivative content creators can challenge redirections
- **Evidence Submission**: Provide proof of originality or fair use
- **Community Voting**: Token-weighted community decision
- **Reversible Outcomes**: Successful disputes can remove redirections

### Dispute Resolution Impact
If a dispute overturns a redirection:
- **Historical Revenue**: Past redirections are not reversed
- **Future Revenue**: Redirection rules removed going forward
- **Badge Potential**: Successful dispute may result in PoC badge issuance
- **Registry Update**: Statistics updated to reflect resolution

The revenue redirection system creates a **fair, transparent, and economically efficient** method for compensating original creators while allowing derivative content to exist and thrive within the MySocial ecosystem. 