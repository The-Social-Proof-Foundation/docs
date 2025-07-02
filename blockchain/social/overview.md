---
icon: share-nodes
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

Your identity on MySocial is more than just a username, it's your on-chain presence, fully owned and controlled by you. With MySocial, your profile, connections, and reputation exist independently of any platform, ensuring true ownership and portability. Unlike traditional social networks, where your identity is locked to a single company, MySocial leverages the blockchain to give users full control over their social graph and content. From human-readable names via Name Service to private and seamless authentication with zkLogin, MySocial ensures both security and accessibility.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td>🔤 <strong>Name Service</strong></td><td>Discover how MySocial's Name Service provides human-readable identities.</td><td></td><td></td><td><a href="name-service.md">name-service.md</a></td></tr><tr><td>🔒 <strong>zkLogin</strong></td><td>Learn how zkLogin enables private and seamless authentication.</td><td></td><td></td><td><a href="zkLogin.md">zkLogin.md</a></td></tr><tr><td>💰 <strong>Tokens</strong></td><td>Explore the future of tokens on MySocial.</td><td></td><td></td><td><a href="broken-reference">Broken link</a></td></tr></tbody></table>

# Social Mechanics

MySocial's social mechanics form the foundation of all user interactions, providing a comprehensive system for content creation, social connections, and community engagement built directly into the blockchain.

## Core Social Features

### 📝 **Posts & Content**
- **Rich Content Support**: Text, images, videos, audio, and mixed media
- **Flexible Post Types**: Standard posts, reposts, quote reposts, and predictions
- **Metadata Integration**: JSON metadata for enhanced functionality
- **Content Permissions**: Granular control over interactions (comments, reactions, reposts)
- **Nested Comments**: Multi-level comment threads with full interaction support

### 👥 **Social Graph & Connections**
- **Following System**: Build and manage social connections
- **Profile-Based Identity**: Blockchain-verified user profiles
- **Social Discovery**: Find and connect with users across platforms
- **Reputation Tracking**: On-chain reputation and social proof
- **Cross-Platform Portability**: Social connections work across all MySocial platforms

### 🎯 **Engagement Mechanics**
- **Reactions**: Emoji and text-based reactions to posts and comments
- **Tips**: Direct MySo token tips to creators and commenters
- **Reposts & Quotes**: Share content with optional commentary
- **Mentions**: Tag users in posts and comments
- **Social Notifications**: Real-time engagement tracking

### 🏛️ **Platform Integration**
- **Multi-Platform Support**: Content and connections work across platforms
- **Platform-Specific Features**: Customizable interaction rules per platform
- **Moderation Tools**: Platform-level content management
- **User Permissions**: Platform join/leave mechanics with approval systems

## Advanced Features

### 🔮 **Prediction Markets**
- **Prediction Posts**: Create posts with multiple outcome options
- **Community Betting**: Users stake MySo tokens on prediction outcomes
- **Automated Resolution**: Smart contract-based outcome determination
- **Reward Distribution**: Winners share the prize pool proportionally
- **Market Analytics**: Track prediction accuracy and user performance

### 📢 **Promoted Content**
- **Content Promotion**: Pay-per-view advertising system
- **View Duration Tracking**: Minimum view times for payment
- **Budget Management**: Set spending limits and view targets
- **Analytics**: Detailed promotion performance metrics
- **Audience Targeting**: Platform-based targeting options

### 🔒 **Gated Content**
- **Subscription Integration**: Posts can require active subscriptions
- **MyIP Integration**: Link posts to encrypted information assets
- **Access Control**: Fine-grained permission management
- **Premium Content**: Monetize exclusive content directly

### 🛡️ **Content Moderation**
- **Community Reporting**: User-driven content flagging system
- **Platform Moderation**: Platform-specific moderation tools
- **Automated Filtering**: Integration with content analysis systems
- **Appeal Processes**: Democratic dispute resolution mechanisms

## Technical Architecture

### Content Management
```move
public struct Post has key, store {
    id: UID,
    owner: address,           // Wallet owner
    profile_id: address,      // Profile reference
    content: String,          // Post content
    media: Option<vector<Url>>, // Media attachments
    post_type: String,        // Post classification
    parent_post_id: Option<address>, // For replies/quotes
    // ... engagement tracking
}
```

### Interaction Tracking
- **Reaction Counts**: Real-time aggregation of all reactions
- **Engagement Metrics**: Likes, comments, reposts, tips
- **Social Proof**: Transparent interaction history
- **Performance Analytics**: Content reach and engagement rates

### Permission System
- **Per-Post Controls**: Enable/disable comments, reactions, reposts, quotes, tips
- **Platform Rules**: Override permissions based on platform policies
- **User Preferences**: Individual user interaction preferences
- **Block List Integration**: Automatic filtering of blocked users

## Integration Points

### Social Proof Tokens
- **Viral Detection**: Social metrics trigger token creation
- **Engagement Weighting**: Comments worth 3x likes, tips worth 10x
- **Real-time Tracking**: Continuous monitoring for viral thresholds
- **Token Integration**: Social proof directly impacts token value

### Proof of Creativity
- **Content Analysis**: All posts analyzed for originality
- **Badge Integration**: PoC badges displayed on posts
- **Revenue Redirection**: Automatic application to social interactions
- **Community Verification**: Social proof supports PoC decisions

### MyIP Integration
- **Gated Posts**: Link posts to encrypted information assets
- **Revenue Sharing**: Tips and token earnings can flow to MyIP
- **Access Control**: Social proof can gate premium content
- **Content Monetization**: Multiple revenue streams per post

## Platform Ecosystem

### Platform Features
- **Custom Branding**: Platforms can customize appearance and rules
- **Revenue Sharing**: Platforms earn from user activity
- **Community Management**: Advanced moderation and admin tools
- **User Onboarding**: Streamlined platform joining processes

### Cross-Platform Benefits
- **Portable Identity**: Profiles work across all platforms
- **Unified Social Graph**: Connections persist between platforms
- **Content Syndication**: Posts can appear on multiple platforms
- **Ecosystem Growth**: Network effects benefit all platforms

## Benefits

### For Users
- **True Ownership**: Blockchain-verified content and social connections
- **Monetization**: Multiple ways to earn from social activity
- **Portability**: Never lose followers or content when switching platforms
- **Privacy Control**: Granular permissions and interaction management

### For Creators
- **Direct Monetization**: Tips, tokens, and premium content sales
- **Audience Ownership**: Followers belong to creator, not platform
- **Content Protection**: PoC system protects original work
- **Analytics**: Detailed performance and engagement data

### For Platforms
- **User Acquisition**: Tap into existing MySocial user base
- **Revenue Generation**: Earn from user activity and transactions
- **Reduced Development**: Core social features provided by protocol
- **Network Effects**: Benefit from ecosystem growth

### For Developers
- **Open Protocol**: Build on standardized social primitives
- **Composability**: Combine social features with custom functionality
- **Interoperability**: Integrate with existing MySocial ecosystem
- **Innovation**: Focus on unique features rather than basic social mechanics

MySocial's social mechanics create a rich, interoperable social ecosystem where users own their data, creators are fairly compensated, and platforms can focus on unique value rather than rebuilding basic social infrastructure.


