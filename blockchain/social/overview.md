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

Your identity on MySocial is more than just a username, it's your on-chain presence, fully owned and controlled by you. With MySocial, your profile, connections, and tokens exist independently of any platform, ensuring true ownership and portability. Unlike traditional social networks, where your identity is locked to a single company, MySocial leverages the blockchain to give users full control over their social graph and content. From human-readable names via Name Service to private and seamless authentication with zkLogin, MySocial ensures both security and accessibility.

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td>🔤 <strong>Name Service</strong></td><td>Discover how MySocial's Name Service provides human-readable identities.</td><td></td><td></td><td><a href="name-service.md">name-service.md</a></td></tr><tr><td>🔒 <strong>zkLogin</strong></td><td>Learn how zkLogin enables private and seamless authentication.</td><td></td><td></td><td><a href="zkLogin.md">zkLogin.md</a></td></tr><tr><td>💰 <strong>Tokens</strong></td><td>Explore the future of tokens on MySocial.</td><td></td><td></td><td><a href="broken-reference">Broken link</a></td></tr></tbody></table>

# Social Mechanics

MySocial's social mechanics are designed to provide a robust, on-chain foundation for user interactions, content creation, and community engagement. Every user has a blockchain-verified profile and social graph, ensuring true ownership and portability of identity, connections, and content across platforms. Features like Name Service and zkLogin further enhance accessibility and privacy.

## Core Social Features

Users can create and share a wide range of content, including text, images, video, and audio. The platform supports flexible post types—such as standard posts, reposts, quotes, and predictions—each with customizable permissions for comments, reactions, and sharing. Nested comments and real-time notifications foster rich, multi-level discussions and engagement. The social graph enables users to build connections, discover new people, and maintain a portable identity and reputation across the ecosystem.

Engagement is further enhanced by features like reactions, direct tips using MySo tokens, and mentions. Platform integration allows for customizable rules, moderation tools, and user permissions, supporting diverse community experiences while leveraging the shared protocol.

## Advanced and Monetization Features

MySocial introduces advanced mechanics such as prediction markets, where users can create posts with multiple outcomes and stake tokens on predictions. Gated content and subscription models allow creators to monetize exclusive posts, with fine-grained access control and integration with encrypted assets via MyIP. Promoted content and pay-per-view advertising are supported, complete with analytics and budget management. Content moderation combines community reporting, platform-specific tools, and automated filtering to maintain a healthy environment.

## Technical Architecture

Content and interactions are managed on-chain using Move structs, providing transparency and composability. For example:

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

Engagement metrics—such as reactions, comments, reposts, and tips—are tracked in real time, providing transparent social proof and analytics. Permissions can be set per post, overridden by platform rules, or customized by user preferences, with block list integration for automatic filtering.

## Integration Points

Social proof tokens are generated when content reaches viral thresholds, with engagement metrics weighted to reflect true influence. The Proof of Creativity system analyzes content for originality and awards badges, while MyIP integration enables gated posts, revenue sharing, and advanced access control.

## Platform Ecosystem and Benefits

Platforms built on MySocial benefit from revenue sharing, advanced moderation, and streamlined audiences. The unified social graph and portable identity system ensure that users and content can move freely between platforms, amplifying network effects and ecosystem growth.

For users, MySocial offers true ownership, monetization opportunities, portability, and privacy controls. Creators enjoy direct monetization, audience ownership, and content protection. Platforms gain access to a broad user base and new revenue streams, while developers can build on open, composable social primitives and focus on innovation.

MySocial's social mechanics create a rich, interoperable ecosystem where users own their data, creators are fairly compensated, and platforms can focus on delivering unique value rather than rebuilding basic social infrastructure.
