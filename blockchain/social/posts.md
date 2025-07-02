---
icon: icons
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

# Posts

MySocial's post protocol provides a comprehensive content management infrastructure built directly into the blockchain, enabling rich social interactions, content monetization, and cross-platform portability.

## Post Types & Features

Posts on MySocial support a variety of content types, including text, images, videos, audio, and mixed media. Each post can include up to 10 media attachments and up to 5,000 characters of content. Mentions allow tagging up to 10 users per post, with automatic notifications. Interactive post types such as reposts, quote reposts, and prediction posts enable dynamic engagement and community-driven content. Nested comment threads support multi-level discussions, and all posts have granular permission controls for comments, reactions, reposts, quotes, and tips.

## Social Interactions

Reactions and engagement are tracked on-chain, providing transparency and real-time analytics. The protocol supports custom emoji or text-based reactions, with a 20-character limit, and records who reacted and how. Tipping is integrated directly into posts and comments, allowing users to send MySo tokens to creators and commenters. Tips are automatically split according to protocol rules, ensuring fair revenue sharing. Comment threads are fully interactive, supporting reactions, tips, and reposts, and are managed with platform-level moderation tools.

```move
// Reaction tracking in smart contract
user_reactions: Table<address, String>,     // User to reaction mapping
reaction_counts: Table<String, u64>,        // Reaction type to count
reaction_count: u64,                        // Total reactions
```

```move
public struct Comment has key, store {
    post_id: address,                    // Parent post
    parent_comment_id: Option<address>,  // For nested comments
    content: String,                     // Comment content
    // ... full interaction support
}
```

## Monetization Integration

Posts are tightly integrated with Social Proof Tokens, enabling viral content to trigger token creation based on engagement metrics. The protocol uses a weighted scoring system (likes, comments, tips) to determine eligibility for tokenization, with revenue from token trading flowing back to the post creator. Proof of Creativity (PoC) ensures originality, awarding badges and redirecting revenue for derivative content. MyIP integration allows posts to be linked to encrypted assets, supporting gated content, premium features, and fine-grained access control.

## Advanced Features

Prediction markets allow users to create posts with multiple betting options, enabling community staking and automated resolution. Promoted content is supported through pay-per-view advertising, with detailed analytics and platform revenue sharing. Content moderation is robust, combining user-driven reporting, platform controls, and transparent records of moderation actions.

```move
public struct PredictionData has key, store {
    options: vector<PredictionOption>,    // Betting options
    bets: vector<PredictionBet>,         // User bets
    resolved: bool,                      // Market resolution status
    winning_option_id: Option<u8>,       // Winning outcome
}
```

## Technical Implementation

Posts are stored on-chain using efficient Move structs, ensuring ownership, portability, and security. Permissions and engagement fields are enforced by smart contracts, and all content is portable across platforms.

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

## Platform Integration

Posts are designed for multi-platform support, with platform-specific rules, unified analytics, and automatic revenue distribution. Security features include blockchain-verified ownership, block list integration, and smart contract-enforced permissions.

## Benefits

For creators, MySocial posts offer true ownership, multiple revenue streams, cross-platform reach, and detailed analytics. Users benefit from rich interactions, investment opportunities, privacy controls, and portable identity. Platforms gain ready-made social infrastructure, revenue generation, and network effects, while focusing on unique value and customization.

MySocial's post system creates a foundation for rich, monetizable social interactions while ensuring creators maintain ownership and control over their content across the entire ecosystem.