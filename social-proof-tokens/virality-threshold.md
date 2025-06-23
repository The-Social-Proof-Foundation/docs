---
icon: fire
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

# Virality Threshold

The virality threshold system determines when content and creators become eligible for Social Proof Token creation. This automated system ensures that only content with demonstrated community engagement can launch tokens, preventing spam and maintaining token quality.

## How Virality Detection Works

### Automated Scoring System
The system continuously monitors content engagement using **weighted scoring algorithms** that value different types of interactions:

**For Post Tokens:**
```
Viral Score = (Likes × 1) + (Comments × 3) + (Tips × 10)
Threshold = 100 points
```

**For Profile Tokens:**
```
Viral Score = (Followers × 1) + (Posts × 1) + (Tips × 5)
Threshold = 100 points
```

### Weight Rationale
The weighting system reflects the value and effort of different engagement types:

- **Likes**: Low weight (1x) - easy, low-commitment interaction
- **Comments**: Medium weight (3x) - requires thought and effort
- **Tips**: High weight (5-10x) - financial commitment demonstrates strong support
- **Followers/Posts**: Base weight (1x) - fundamental platform metrics

## Technical Implementation

### Automated Scoring System
The system continuously monitors content engagement and automatically calculates viral scores in real-time, triggering eligibility notifications when thresholds are reached.

### Real-Time Monitoring
The system provides **sub-second transaction processing** and **high-volume tracking** capabilities that monitor:
- Live engagement metrics as they occur
- Cumulative scoring across all content interactions
- Instant threshold crossing detection
- Automatic eligibility status updates

### Threshold Crossing
When content reaches the viral threshold:
1. **Eligibility Achieved**: Content becomes eligible for token auction
2. **Creator Notification**: Owner receives notification of eligibility
3. **Manual Initiation**: Creator must manually start the auction process
4. **Public Visibility**: Eligible content may be highlighted for community awareness

## Threshold Configuration

### Default Values
**Post Viral Scoring:**
- Likes Weight: 1
- Comments Weight: 3
- Tips Weight: 10
- Viral Threshold: 100 points

**Profile Viral Scoring:**
- Followers Weight: 1
- Posts Weight: 1
- Tips Weight: 5
- Viral Threshold: 100 points

### Governance Adjustability
All threshold parameters can be adjusted through governance mechanisms using community voting processes.

**Governance Controls:**
- **Weight Adjustments**: Modify the importance of different engagement types
- **Threshold Changes**: Raise or lower the minimum viral score required
- **Type-Specific Rules**: Different thresholds for posts vs profiles
- **Platform Adaptation**: Adjust thresholds based on platform growth and activity

## Eligibility Examples

### Post Token Eligibility Scenarios

**Scenario 1: Viral Meme**
- 50 likes + 10 comments + 2 MySo tips = 50 + 30 + 20 = 100 points ✅
- **Result**: Reaches threshold, eligible for token auction

**Scenario 2: High-Engagement Discussion**
- 20 likes + 25 comments + 1 MySo tip = 20 + 75 + 10 = 105 points ✅
- **Result**: Exceeds threshold through comment engagement

**Scenario 3: Premium Content**
- 10 likes + 5 comments + 8 MySo tips = 10 + 15 + 80 = 105 points ✅
- **Result**: Tips-driven virality demonstrates strong value

**Scenario 4: Low Engagement**
- 30 likes + 5 comments + 0 tips = 30 + 15 + 0 = 45 points ❌
- **Result**: Below threshold, not eligible

### Profile Token Eligibility Scenarios

**Scenario 1: Active Creator**
- 80 followers + 15 posts + 2 MySo tips = 80 + 15 + 10 = 105 points ✅
- **Result**: Well-rounded profile activity

**Scenario 2: Premium Creator**
- 50 followers + 10 posts + 8 MySo tips = 50 + 10 + 40 = 100 points ✅
- **Result**: High-value creator with supporter tips

**Scenario 3: Growing Account**
- 90 followers + 8 posts + 0 tips = 90 + 8 + 0 = 98 points ❌
- **Result**: Close but needs more engagement

## Quality Assurance Features

### Anti-Gaming Mechanisms
The system includes several protections against artificial inflation:

**Engagement Quality Checks:**
- Tips require actual MySo token transfers (can't be faked)
- Comments and reactions tracked through verified user interactions
- Follower counts based on authenticated profile connections

**Block List Integration:**
- Blocked users' engagement doesn't count toward viral scores
- Prevents artificial inflation through sock puppet accounts
- Maintains genuine community engagement standards

**Rate Limiting:**
- Natural engagement patterns expected for sustainable virality
- Sudden spikes may trigger additional verification
- Organic growth patterns favored over manipulation

### Threshold Integrity
**Transparent Calculation:**
- All scoring formulas are public and verifiable
- Real-time score tracking available to content creators
- Community can verify threshold calculations independently

**Fair Opportunity:**
- Same thresholds apply to all users and content types
- No preferential treatment based on account status
- Merit-based system rewards genuine engagement

## Strategic Implications

### For Content Creators
**Optimization Strategies:**
- **Engagement Focus**: Create content that encourages comments and discussion
- **Value Proposition**: High-quality content attracts tips
- **Community Building**: Foster genuine follower relationships
- **Consistency**: Regular posting helps profile token eligibility

**Threshold Planning:**
- Monitor viral score progress toward threshold
- Understand which engagement types drive scoring
- Time content releases for maximum community engagement
- Build sustainable engagement rather than gaming metrics

### For Community Members
**Investment Insight:**
- Viral threshold crossing indicates proven community interest
- Higher viral scores suggest stronger token potential
- Engagement quality reflects content/creator sustainability
- Threshold achievement demonstrates minimum viable interest

### For Platforms
**Ecosystem Health:**
- Viral thresholds ensure quality token launches
- Prevents spam tokens that dilute ecosystem value
- Creates natural filtering mechanism for worthwhile investments
- Maintains high standards for tokenized social proof

The virality threshold system creates a **merit-based gateway** that ensures only content and creators with demonstrated community value can launch Social Proof Tokens, maintaining ecosystem quality while providing clear, achievable goals for creators.

*Emergency trading controls may be activated by governance in exceptional circumstances.* 