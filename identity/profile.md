---
icon: id-card
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

# Profile

Your MySocial profile is the foundation of your on-chain identity, providing a comprehensive digital representation that you fully own and control. Unlike traditional social platforms where your profile exists at the mercy of centralized companies, MySocial profiles are built on blockchain technology, ensuring true ownership, portability, and transferability.

## Key Features

### Self-Sovereign Identity

Your profile data is stored on-chain with cryptographic verification, giving you complete control over your digital identity. Each profile is immutable once created, with attached usernames that cannot be altered, and only one profile may be associated with each wallet.

### Portable Social Graph

Your connections, followers, and social relationships are part of your on-chain profile, allowing you to maintain your social network across different applications and platforms in the MySocial ecosystem.

### Profile as an Asset

Your profile serves as a scarce identity anchor that can appreciate in value based on social impact and network recognition. High-value usernames or accounts with substantial followings can be sold as transferable assets, allowing you to monetize your social presence.

### Ownership Transfer Rights

Profile ownership can be transferred through asset sales, creating a marketplace for valuable digital identities. When a profile is sold, the new owner acquires the username and follower base, but not the original content such as posts or social interactions, preserving the distinction between identity and authored history.

## Technical Implementation

Profiles are implemented as on-chain records associated with your MySocial identity. Each profile consists of:

- Core identity reference linked to your wallet
- Metadata storage for profile information
- Social graph connections
- Reputation attestations
- Content ownership records
- Transferable ownership rights

The profile module interacts with other key components of the MySocial ecosystem:

- **Name Service**: Human-readable names that are linked to your profile
- **zkLogin**: Authentication mechanism for accessing and updating your profile
- **Social Graphs**: Networks of connections built around your profile

<table data-view="cards"><thead><tr><th></th><th></th><th data-hidden data-card-cover data-type="files"></th><th data-hidden></th><th data-hidden data-card-target data-type="content-ref"></th></tr></thead><tbody><tr><td>🔤 <strong>Name Service</strong></td><td>Connect your profile to a human-readable identity.</td><td></td><td></td><td><a href="name-service.md">name-service.md</a></td></tr><tr><td>👥 <strong>Social Graphs</strong></td><td>Explore how profiles connect in the social network.</td><td></td><td></td><td><a href="social-graphs.md">social-graphs.md</a></td></tr><tr><td>⭐ <strong>Reputation</strong></td><td>Learn how on-chain reputation works with profiles.</td><td></td><td></td><td><a href="reputation.md">reputation.md</a></td></tr></tbody></table> 