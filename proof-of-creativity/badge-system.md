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

When a post with media content is created, the system automatically triggers PoC analysis. The oracle processes the content using CLIP embeddings for images, acoustic fingerprinting for audio, and frame extraction for video. The system compares similarity scores against a 95% threshold. If the content is original, a unique PoC badge ID is generated, linked to the post, and recorded in the PoC registry.

## Badge Properties

Each badge has a unique identifier, is immutable once issued (except through disputes), is timestamped, and is media-specific. Badges are permanently associated with the post and tracked in the PoC registry.

## Badge Benefits

For content creators, PoC badges provide verifiable proof of originality, enhanced reputation, social recognition, economic advantages, and legal protection. For Social Proof Tokens, badges increase token pool value, market confidence, and revenue optimization. Platforms benefit from higher content quality, user trust, reduced disputes, and improved content algorithms.

## Badge Display and Verification

Badges are visually indicated on posts with icons, checkmarks, and metadata. Anyone can verify a badge by querying the blockchain, inspecting the post's badge field, or reviewing the PoC registry and event history.

## Badge Statistics and Analytics

The PoC Registry tracks badge issuance rates, media type breakdowns, creator performance, platform activity, and originality trends over time.

## Integration with Ecosystem

PoC badges automatically integrate with token economics, MyIP intellectual property claims, and platform features like search, recommendations, and moderation. Badge holders receive discoverability benefits and may be eligible for enhanced platform programs.

## Badge Lifecycle

Badges are created when content passes originality analysis, minted as unique IDs, and linked to posts. They are immutable but can be challenged through the community dispute process. Badge history is permanently maintained and recognized across the MySocial ecosystem.

The PoC badge system creates a trusted, transparent, and economically valuable verification system that benefits creators, platforms, and the broader MySocial ecosystem while maintaining community governance over disputed cases. 