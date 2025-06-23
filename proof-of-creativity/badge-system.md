---
icon: award
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

# PoC Badge System

The Proof of Creativity badge system recognizes and verifies original content on MySocial. When content passes the originality verification process, it receives a **PoC badge** that serves as permanent proof of creativity and authenticity.

## What is a PoC Badge?

A PoC badge is an **on-chain verification** that content has been analyzed by the oracle system and determined to be original. It provides:

- **Authenticity Proof**: Verified original content status
- **Creator Credibility**: Enhanced reputation for content creators  
- **Discoverability**: Improved content visibility and search ranking
- **Economic Benefits**: Enhanced value for Social Proof Tokens
- **Historical Record**: Permanent on-chain timestamp of originality

## Badge Issuance Process

### 1. Content Submission
When a post with media content is created, the system automatically triggers PoC analysis through the `create_post` function.

### 2. Oracle Analysis
The oracle system processes the content:
- **Image Analysis**: CLIP embeddings generate 512-dimensional vectors
- **Audio Analysis**: Shazam-style acoustic fingerprinting creates unique hashes
- **Video Analysis**: Frame extraction plus audio track processing
- **Database Search**: Timescale Vector AI searches for similar content

### 3. Originality Determination
The oracle compares similarity scores against thresholds:
- **Below 95% similarity**: Content considered original
- **Oracle confidence**: High/medium/low confidence levels provided
- **Original creator detection**: If similarity found, identifies potential source

### 4. Smart Contract Decision
The oracle calls `analyze_and_update_post` with the similarity analysis results.

If content is determined original (similarity < threshold):
- **Badge Creation**: Unique PoC badge ID generated
- **Post Update**: Badge ID linked to post permanently
- **Registry Update**: Badge count incremented in PoC registry
- **Event Emission**: Badge issuance broadcasted to network

## Badge Properties

### Technical Structure
Each post contains optional PoC badge information and revenue redirection settings that are automatically managed by the system.

### Badge Characteristics
- **Unique Identifier**: Each badge has a distinct ID
- **Immutable**: Once issued, badges cannot be revoked (except through disputes)
- **Timestamped**: Creation time permanently recorded
- **Media-Specific**: Badge type reflects content media type (image/video/audio)
- **Post-Linked**: Badge permanently associated with specific post

## Badge Benefits

### For Content Creators
- **Proof of Originality**: Verifiable evidence of content authenticity
- **Enhanced Reputation**: Increased credibility and trustworthiness
- **Social Recognition**: Visual indicator of creativity and originality
- **Economic Advantages**: Potential for premium monetization
- **Legal Protection**: On-chain evidence for intellectual property claims

### For Social Proof Tokens
- **Value Enhancement**: PoC badges increase token pool attractiveness
- **Confidence Signal**: Market confidence in authentic content creator
- **Revenue Optimization**: No revenue redirection = full creator compensation
- **Trading Premium**: Original content tokens command higher prices

### For Platforms
- **Content Quality**: Higher quality content with verified authenticity
- **User Trust**: Enhanced platform credibility through verification
- **Reduced Disputes**: Clear originality evidence reduces conflicts
- **Algorithm Benefits**: Authentic content prioritized in feeds

## Badge Display and Verification

### Visual Indicators
- **Badge Icon**: Distinctive visual marker on posts
- **Verification Checkmark**: Clear originality indication
- **Metadata Display**: Badge information accessible to users
- **Time Stamp**: Creation time and verification date shown

### Verification Process
Anyone can verify a badge by:
1. **On-Chain Lookup**: Query blockchain for badge details
2. **Post Inspection**: Check post's `poc_badge_id` field
3. **Registry Confirmation**: Verify badge in PoC registry
4. **Event History**: Review badge issuance events

## Badge Statistics and Analytics

The PoC Registry tracks comprehensive badge statistics including total badges issued, revenue redirections created, disputes submitted, and votes cast.

### Available Metrics
- **Badge Issuance Rate**: Badges issued over time
- **Media Type Breakdown**: Distribution across image/video/audio
- **Creator Performance**: Badge counts per creator
- **Platform Activity**: Badge issuance by platform
- **Quality Trends**: Originality rates over time

## Integration with Ecosystem

### Social Proof Tokens
PoC badges automatically integrate with token economics:
- **Token Pool Enhancement**: Badges increase pool value perception
- **Revenue Clarity**: No redirection confusion for investors
- **Market Confidence**: Clear originality signal for trading
- **Automatic Sync**: Badge status synchronized with token pools

### MyIP Integration  
PoC badges complement MyIP intellectual property system:
- **Originality Evidence**: Badges support IP ownership claims
- **Licensing Benefits**: Original content commands premium licensing fees
- **Legal Standing**: Blockchain evidence for legal proceedings
- **Attribution Tracking**: Clear creator identification

### Platform Features
- **Search Enhancement**: Badge holders receive discoverability benefits
- **Recommendation Systems**: Original content prioritized in algorithms  
- **Moderation Assistance**: Badges help identify authentic vs duplicate content
- **Creator Programs**: Badge holders eligible for enhanced platform benefits

## Badge Lifecycle

### Creation
1. **Content Posted**: Media content submitted to platform
2. **Oracle Analysis**: Automated similarity detection performed
3. **Originality Confirmed**: Content passes threshold requirements
4. **Badge Minted**: Unique badge ID created and linked to post
5. **Notification**: Creator notified of badge issuance

### Maintenance
- **Immutable Status**: Badges cannot be modified post-issuance
- **Dispute Protection**: Community dispute system provides recourse
- **Historical Preservation**: Badge history permanently maintained
- **Cross-Platform Recognition**: Badges recognized across MySocial ecosystem

### Potential Revocation
Only through community dispute process:
- **Dispute Filing**: Challenge must be submitted with stake
- **Community Voting**: Token-weighted community decision
- **Evidence Review**: Comprehensive evaluation of originality claims
- **Democratic Resolution**: Community consensus determines outcome

The PoC badge system creates a trusted, transparent, and economically valuable verification system that benefits creators, platforms, and the broader MySocial ecosystem while maintaining community governance over disputed cases. 