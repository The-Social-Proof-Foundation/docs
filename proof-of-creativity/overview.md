---
icon: certificate
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

Content ownership is a core pillar of MySocial, ensuring that creators have full control over their work, identity, and audience. Unlike traditional social platforms that claim rights over user-generated content, MySocial records ownership on-chain, preventing unauthorized use and ensuring creators receive proper recognition and monetization opportunities. Intellectual property protection, proof of creativity, and fair content moderation all stem from this foundation, making content ownership essential to a more transparent and user-driven social experience.  

With MySocial's **Proof of Creativity** protocol, original content is not only protected but also rewarded. If someone copies and pastes content without making significant changes, the system can recognize the original creator and automatically redirect monetization to them. This ensures that creativity is properly attributed and prevents low-effort duplication from profiting unfairly. Content remains accessible, portable across platforms, and protected against censorship while still allowing communities to implement their own moderation policies. This approach ensures that creators—not corporations—dictate how their content is used, shared, and monetized across the ecosystem.

# Proof of Creativity (PoC)

Proof of Creativity is MySocial's **content ownership and revenue redistribution system** that automatically detects derivative content and ensures original creators receive fair compensation for their work.

## What Proof of Creativity Actually Does

PoC is **NOT** just about content verification. It's a comprehensive system for **content ownership protection and automatic revenue redistribution**:

### 🔍 **Automated Content Analysis**
- Oracle-based similarity detection for images, videos, and audio
- Configurable similarity thresholds per media type (default 95%)
- Advanced content fingerprinting and comparison algorithms
- Real-time analysis of newly posted content

### 🏆 **PoC Badge System**
- **Original Content**: Receives a PoC badge for verified unique content
- **Badge Benefits**: Enhanced discoverability and creator credibility
- **Automatic Integration**: Badges sync with Social Proof Token pools
- **Community Recognition**: Visual proof of content originality

### 💰 **Revenue Redistribution Engine**
- **Automatic Detection**: When similarity exceeds threshold, revenue is redirected
- **Dynamic Percentage**: Redirection amount scales with similarity score
- **Real-time Application**: Immediate effect on all future earnings
- **Token Pool Sync**: Social Proof Tokens automatically redirect revenue

### ⚖️ **Community Dispute System**
- **Stake-based Voting**: Community can challenge PoC decisions
- **Economic Incentives**: Winning voters share rewards from losing side
- **Dispute Types**: Challenge badges or revenue redirections
- **Democratic Resolution**: Community consensus determines outcomes

## How It Works

### 1. Content Submission & Analysis
When content is posted:
1. Oracle analyzes content for similarity to existing works
2. Compares against similarity threshold for media type
3. Identifies potential original creators if similarity found
4. Makes automated decision: Badge or Redirection

### 2. PoC Badge Issuance
For original content (below similarity threshold):
- PoC badge automatically issued to post
- Badge ID linked to post permanently
- Enhanced social proof and discoverability
- Integration with Social Proof Token economics

### 3. Revenue Redirection
For derivative content (above similarity threshold):
- Calculates redirection percentage based on similarity score
- Automatically redirects revenue to original creator
- Applies to all monetization (tips, token sales, etc.)
- Updates in real-time across all systems

### 4. Community Governance
- Post owners can dispute PoC decisions
- Community votes with MYS tokens at stake
- Winning side shares rewards from losing voters
- Democratic resolution of edge cases

## Technical Implementation

### Similarity Thresholds
- **Images**: 95% similarity threshold
- **Videos**: 95% similarity threshold  
- **Audio**: 95% similarity threshold
- **Configurable**: Adjustable by governance

### Revenue Redirection Formula
```
Delta = (Similarity Score - Threshold) / (100 - Threshold)
Redirect % = (Base Redirect % × Delta Percentage)
```

### Dispute Mechanics
- **Dispute Cost**: 5 MYS + 1 MYS protocol fee
- **Voting Period**: 7 epochs
- **Stake Range**: 1-100 MYS per vote
- **Resolution**: Stake-weighted voting determines outcome

## Integration Points

### Social Proof Tokens
- PoC badges enhance token pool value
- Revenue redirections automatically apply to token earnings
- Community confidence reflected in token prices

### MyIP Integration
- PoC can be applied to encrypted MyIP content
- Revenue redirections apply to MyIP sales
- Original creators protected across all monetization

### Platform Features
- Automatic moderation assistance
- Content authenticity verification
- Creator protection and fair compensation

## Benefits

### For Original Creators
- **Automatic Protection**: No manual claims needed
- **Fair Compensation**: Receive revenue from derivative works
- **Enhanced Credibility**: PoC badges prove originality
- **Community Support**: Dispute system provides recourse

### For Platforms
- **Reduced Moderation**: Automated content verification
- **Legal Protection**: Clear ownership and attribution
- **User Trust**: Transparent content authenticity
- **Economic Incentives**: Fair creator compensation

### For the Ecosystem
- **Quality Content**: Incentivizes original creation
- **Fair Economy**: Ensures creators are compensated
- **Community Governance**: Democratic dispute resolution
- **Transparency**: All decisions and redirections are public

Proof of Creativity creates a self-regulating ecosystem where original content is rewarded and derivative works fairly compensate their sources, fostering a sustainable creative economy.