---
icon: building
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

# Platforms

MySocial's platform protocol empowers anyone to launch and operate a social media platform, all while leveraging the shared infrastructure, user base, and monetization features of the MySocial ecosystem. Whether you're building a niche community or a large-scale network, the protocol provides the tools and flexibility needed to create a unique experience.

## Platform Creation & Management

To get started, developers define key platform attributes such as name, tagline, branding, and links:

```move
public struct Platform has key {
    name: String,                    // Platform name
    tagline: String,                 // Short description
    description: String,             // Detailed description
    logo: String,                    // Platform logo URL
    developer: address,              // Platform owner/developer
    terms_of_service: String,        // ToS URL
    privacy_policy: String,          // Privacy policy URL
    platforms: vector<String>,       // Platform names/identifiers
    links: vector<String>,           // Platform URLs
    status: PlatformStatus,          // Development status
    treasury: Balance<MYS>,          // Platform treasury
}
```

**Lifecycle stages:**
- Development
- Alpha
- Beta
- Live
- Maintenance
- Sunset
- Shutdown

Each stage reflects the platform's operational status, from initial creation to full production and eventual deprecation if needed. Platforms can be customized with branding, terms, and policies, and support web, mobile, and desktop applications. Developers have full control over platform management, including moderation and user management tools.

## User Management

Users can join any approved platform using their existing MySocial profiles, ensuring seamless cross-platform identity. Each platform can offer custom features and support easy migration between platforms. Moderation is handled through a combination of code-based controls and community guidelines:

```move
// Platform moderation capabilities
moderators: VecSet<address>,           // Platform moderators
blocked_profiles: VecSet<address>,     // Blocked users
joined_profiles: VecSet<address>,      // Platform members
```

Moderators can be added or removed, users can be blocked, and content policies are enforced at the platform level. Dispute resolution and appeals are supported for moderation decisions. Users explicitly join platforms they wish to use, and content can be syndicated across multiple platforms. Each platform curates its own feed, but the unified social graph ensures connections persist across the ecosystem.

## Governance & Economics

Each platform maintains a treasury for managing funds and distributing incentives:

```move
treasury: Balance<MYS>,              // Platform MySo treasury
```

Platforms earn fees from user activity, manage their own funds, and can distribute tokens to users and moderators. Incentives are available for active participation, and platforms are designed for economic sustainability.

**Optional DAO governance:**
Platforms can enable community-driven decisions with configurable parameters:

```move
wants_dao_governance: bool,           // Enable DAO governance
delegate_count: Option<u64>,          // Number of delegates
voting_period_epochs: Option<u64>,    // Voting duration
quorum_votes: Option<u64>,           // Required votes for proposals
```

DAO governance enables democratic decision-making, proposal submission, and voting, with options for quadratic voting and shared platform ownership.

**Revenue streams include:**
- Trading fees from Social Proof Token trading
- Content tips
- MyIP sales
- Advertising
- Subscription services

These mechanisms support both platform operations and creator incentives.

## Integration with MySocial Features

Platforms can issue their own tradeable tokens, support creator tokens, and participate in revenue sharing from token trading. Token holders may have governance rights and participate in platform decisions. Proof of Creativity ensures content protection and quality, with revenue redirection and dispute resolution available for original creators. MyIP integration allows platforms to host encrypted premium content, manage access, and offer enhanced monetization tools for creators.

## Platform Types & Use Cases

MySocial supports a wide range of platform types, from general social networks and niche communities to professional, creator, and discussion platforms. Specialized use cases include gaming, education, marketplaces, news, entertainment, and enterprise solutions such as internal company networks, brand communities, and event platforms.

## Developer Tools & APIs

Developers have access to:
- Creation tools and customization APIs
- SDKs for TypeScript and Rust
- Testing frameworks for platform development
- Management dashboards for analytics, moderation, treasury, and user management
- APIs for programmatic management of platforms, users, content, and analytics, as well as integration with external services

## Benefits

Platform creators benefit from low barriers to entry, shared infrastructure, a built-in user base, and ready-to-use monetization features. Users enjoy platform choice, portable identity, advanced features, and investment opportunities. The ecosystem as a whole benefits from innovation, competition, specialization, and sustainable growth supported by platform fees.

## Platform Approval & Quality

New platforms undergo an initial review for compliance and must meet minimum quality standards and community guidelines. Ongoing monitoring and community feedback help maintain quality and adherence to ecosystem standards. Key metrics include user engagement, content quality, community health, platform stability, and innovation.

> MySocial's platform system enables a diverse ecosystem of social media experiences, all benefiting from shared infrastructure, portable identity, and unified monetization features.
