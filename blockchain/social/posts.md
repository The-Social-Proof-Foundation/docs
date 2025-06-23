---
icon: picture
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

# Posts & Content Protocol

MySocial's post protocol provides a comprehensive content management infrastructure built directly into the blockchain, enabling rich social interactions, content monetization, and cross-platform portability.

## Post Types & Features

### Standard Posts
- **Rich Content Support**: Text, images, videos, audio, and mixed media
- **Metadata Integration**: JSON metadata for enhanced functionality
- **Media URLs**: Support for up to 10 media attachments per post
- **Content Limits**: 5,000 character limit for post content
- **Mentions System**: Tag up to 10 users per post with automatic notifications

### Interactive Post Types
- **Reposts**: Share existing content with attribution to original creator
- **Quote Reposts**: Add commentary while sharing original content
- **Prediction Posts**: Create community betting markets on future outcomes
- **Comment Threads**: Nested comment system with full interaction support

### Content Permissions
Each post has granular permission controls:
- **Allow Comments**: Enable/disable comment threads
- **Allow Reactions**: Control emoji and text reactions
- **Allow Reposts**: Permit content sharing
- **Allow Quotes**: Enable quote reposts with commentary
- **Allow Tips**: Accept direct MySo token tips

## Social Interactions

### Reactions & Engagement
```move
// Reaction tracking in smart contract
user_reactions: Table<address, String>,     // User to reaction mapping
reaction_counts: Table<String, u64>,        // Reaction type to count
reaction_count: u64,                        // Total reactions
```

- **Custom Reactions**: Emoji or text-based reactions (20 character limit)
- **Reaction Analytics**: Real-time aggregation of all reaction types
- **User Tracking**: Transparent record of who reacted and how
- **Engagement Metrics**: Used for Social Proof Token viral thresholds

### Tipping System
- **Direct Tips**: Send MySo tokens directly to post creators
- **Comment Tips**: Tip commenters with automatic revenue sharing
  - **80%** goes to commenter
  - **20%** goes to original post owner
- **Repost Tips**: Tips on reposts split 50/50 between reposter and original creator
- **Tip Tracking**: All tips recorded on-chain for transparency

### Comment System
```move
public struct Comment has key, store {
    post_id: address,                    // Parent post
    parent_comment_id: Option<address>,  // For nested comments
    content: String,                     // Comment content
    // ... full interaction support
}
```

- **Nested Comments**: Multi-level comment threads
- **Full Interactions**: Comments support reactions, tips, and reposts
- **Content Management**: Same rich media support as posts
- **Moderation**: Platform-level comment management tools

## Monetization Integration

### Social Proof Tokens
Posts automatically integrate with the token system:
- **Viral Detection**: Engagement metrics trigger token creation
- **Weighted Scoring**: 
  - Likes: 1 point each
  - Comments: 3 points each  
  - Tips: 10 points each
- **Threshold**: 100 points triggers token eligibility
- **Revenue Sharing**: Token trading fees flow back to post creator

### Proof of Creativity
All posts are analyzed for originality:
- **Automatic Analysis**: Oracle-based content similarity detection
- **PoC Badges**: Original content receives verification badges
- **Revenue Redirection**: Derivative content automatically redirects earnings to original creators
- **Community Disputes**: Post owners can challenge PoC decisions through voting

### MyIP Integration
Posts can be linked to encrypted information assets:
- **Gated Content**: Require MyIP purchase for full access
- **Premium Features**: Link posts to subscription-based content
- **Revenue Correlation**: MyIP sales can boost Social Proof Token value
- **Access Control**: Fine-grained permission management

## Advanced Features

### Prediction Markets
```move
public struct PredictionData has key, store {
    options: vector<PredictionOption>,    // Betting options
    bets: vector<PredictionBet>,         // User bets
    resolved: bool,                      // Market resolution status
    winning_option_id: Option<u8>,       // Winning outcome
}
```

- **Multi-Option Betting**: Up to 10 prediction outcomes per post
- **Community Staking**: Users bet MySo tokens on prediction outcomes
- **Automated Resolution**: Smart contract-based outcome determination
- **Reward Distribution**: Winners share prize pool proportionally
- **Platform Fees**: Configurable fees for prediction market operation

### Promoted Content
- **Pay-per-View**: Advertisers pay for guaranteed content views
- **View Duration Tracking**: Minimum 3-second view requirement
- **Budget Management**: Set spending limits and view targets
- **Analytics**: Detailed performance metrics for promoted content
- **Platform Revenue**: Platforms earn from promotion activity

### Content Moderation
- **Community Reporting**: User-driven content flagging system
- **Platform Controls**: Platform-specific moderation tools
- **Removal Tracking**: Transparent record of content moderation actions
- **Appeal Process**: Democratic dispute resolution for moderation decisions

## Technical Implementation

### Content Storage
```move
public struct Post has key, store {
    owner: address,                      // Wallet owner
    profile_id: address,                 // Profile reference
    content: String,                     // Post content
    media: Option<vector<Url>>,          // Media attachments
    post_type: String,                   // Post classification
    parent_post_id: Option<address>,     // For replies/quotes
    created_at: u64,                     // Creation timestamp
    // ... engagement and permission fields
}
```

### Platform Integration
- **Multi-Platform Support**: Posts appear across multiple platforms
- **Platform-Specific Rules**: Override permissions based on platform policies
- **Cross-Platform Analytics**: Unified engagement tracking
- **Revenue Distribution**: Automatic fee splitting between stakeholders

### Security & Privacy
- **Ownership Verification**: Blockchain-verified content ownership
- **Block List Integration**: Automatic filtering of blocked users
- **Permission Enforcement**: Smart contract-enforced interaction rules
- **Data Portability**: Content ownership independent of platform

## Benefits

### For Creators
- **True Ownership**: Blockchain-verified content ownership
- **Multiple Revenue Streams**: Tips, tokens, MyIP, and promotion earnings
- **Cross-Platform Reach**: Content works across all MySocial platforms
- **Analytics**: Detailed engagement and performance data
- **Protection**: PoC system protects against content theft

### For Users
- **Rich Interactions**: Comprehensive engagement options
- **Investment Opportunities**: Social Proof Tokens for content speculation
- **Community Participation**: Prediction markets and governance voting
- **Privacy Control**: Granular permission management
- **Portable Identity**: Interactions tied to user, not platform

### For Platforms
- **Ready-Made Features**: Complete social infrastructure provided
- **Revenue Generation**: Earn from tips, tokens, and promotion activity
- **Network Effects**: Benefit from ecosystem-wide content and users
- **Customization**: Platform-specific features and branding
- **Reduced Development**: Focus on unique value rather than basic features

MySocial's post system creates a foundation for rich, monetizable social interactions while ensuring creators maintain ownership and control over their content across the entire ecosystem.
