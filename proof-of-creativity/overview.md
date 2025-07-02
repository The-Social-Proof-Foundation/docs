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

Content ownership is a core pillar of MySocial, ensuring creators have full control over their work, identity, and audience. Unlike traditional social platforms that claim rights over user-generated content, MySocial records ownership on-chain, preventing unauthorized use and ensuring creators receive proper recognition and monetization opportunities. Intellectual property protection, proof of creativity, and fair content moderation all stem from this foundation, making content ownership essential to a more transparent and user-driven social experience.

With MySocial's Proof of Creativity (PoC) protocol, original content is protected and rewarded. The system recognizes the original creator of content and can automatically redirect monetization to them if someone copies and pastes content without significant changes. This ensures creativity is properly attributed and prevents low-effort duplication from profiting unfairly. Content remains accessible, portable across platforms, and protected against censorship, while still allowing communities to implement their own moderation policies. Creators—not corporations—dictate how their content is used, shared, and monetized across the ecosystem.

<figure><picture><source srcset="../.gitbook/assets/Proof-of-Creativity (3).png" media="(prefers-color-scheme: dark)"><img src="../.gitbook/assets/Proof-of-Creativity - Light (2).png" alt=""></picture><figcaption></figcaption></figure>

## Proof of Creativity (PoC)

PoC is MySocial's content ownership and revenue redistribution system that automatically detects derivative content and ensures original creators receive fair compensation for their work. It is not just about content verification, but a comprehensive system for content ownership protection and automatic revenue redistribution.

### Automated Content Analysis

The system uses oracle-based similarity detection for images, videos, and audio, with configurable similarity thresholds (default 95%). Advanced fingerprinting and comparison algorithms provide real-time analysis of newly posted content.

### PoC Badge System

Original content receives a PoC badge for verified uniqueness, which enhances discoverability and creator credibility. Badges are automatically integrated with Social Proof Token pools and provide visual proof of content originality.

### Revenue Redistribution Engine

When similarity exceeds the threshold, revenue is redirected to the original creator. The redirection amount scales with the similarity score and is applied in real time to all future earnings, including Social Proof Token pools.

### Community Dispute System

Community members can challenge PoC decisions through stake-based voting. Economic incentives reward accurate voting, and the system supports challenges to badges or revenue redirections, with democratic resolution by community consensus.

## How It Works

When content is posted, the oracle analyzes it for similarity to existing works. If the content is original (below the similarity threshold), a PoC badge is issued and linked to the post. For derivative content (above the threshold), the system calculates a redirection percentage based on the similarity score and automatically redirects revenue to the original creator. All monetization, including tips and token sales, is updated in real time. Post owners can dispute PoC decisions, with the community voting on the outcome.

## Technical Implementation

Similarity thresholds are set at 95% for images, videos, and audio by default, but are configurable by governance. The revenue redirection formula is:

```
Delta = (Similarity Score - Threshold) / (100 - Threshold)
Redirect % = (Base Redirect % × Delta Percentage)
```

Disputes cost 5 MySo plus a 1 MySo protocol fee, with a 7-epoch voting period and a stake range of 1-100 MySo per vote. Stake-weighted voting determines the outcome.

## Integration Points

PoC badges enhance token pool value and automatically apply revenue redirections to token earnings. The system integrates with MyIP for encrypted content and supports platform features like moderation assistance and content authenticity verification.

## Benefits

Original creators benefit from automatic protection, fair compensation, and enhanced credibility. Platforms gain reduced moderation costs, legal protection, and user trust. The ecosystem as a whole benefits from quality content, a fair economy, community governance, and transparency.

Proof of Creativity creates a self-regulating ecosystem where original content is rewarded and derivative works fairly compensate their sources, fostering a sustainable creative economy.
