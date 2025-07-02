---
icon: server
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

# Site Hosting

MySocial Site Hosting allows users to deploy fully decentralized websites using the same principles as MyIP and file storage. This system eliminates the need for traditional web hosting infrastructure by leveraging MySocial's decentralized storage network. Developers and creators can seamlessly publish, update, and manage websites using MySo tokens, making them censorship-resistant and persistently available.

Sites hosted on MySocial function similarly to traditional static websites but are distributed, verifiable, and tamper-proof. They can be associated with a MySocial username or content-based identifier, offering human-readable domain options for easy accessibility.

{% hint style="info" %}
Site Hosting will be avalible post-mainnet launch.
{% endhint %}

## Features of MySocial Site Hosting

MySocial Site Hosting requires no traditional servers. Users simply upload their site's source files, pay storage fees in MySo tokens, and MySocial handles storage and retrieval through the decentralized network. Sites can use MySocial usernames or generated content-based identifiers for easy access.

Sites are stored as on-chain objects and can be transferred between owners, but they maintain immutable versioning. No central authority can take down websites once they're published to the network. Sites integrate directly with MySocial identity systems, linking to MyIP content, profiles, and other MySocial assets.

The system supports subscription models where creators can store encrypted media and provide decryption keys only to paid subscribers or users who purchase content. While MySocial provides the decentralized storage, decryption happens client-side. This enables fully decentralized web experiences, including all required resources such as JavaScript, CSS, HTML, and media files.

## Technical Architecture

### Decentralized Storage Foundation

All MySocial-hosted sites utilize the same file storage system that powers the rest of the platform. Files are fragmented using Red Hat encoding and distributed across multiple storage nodes for redundancy. Data retrieval is optimized using content-addressable storage, ensuring that sites load quickly and reliably from the closest available nodes.

Availability is maintained through storage proofs and MySo token incentives for storage nodes. When users visit a MySocial-hosted site, their browser retrieves metadata from the blockchain and fetches necessary assets from the distributed storage network.

### Site Access and Addressing

MySocial Site Hosting operates on a subdomain system where MySocial usernames serve as human-readable domain names (e.g., `yourname.mysocial.site`). Base36 encoded object IDs provide unique identifiers for site retrieval (e.g., `abcdef123456.mysocial.site`). Custom namespaces allow for personal branding and domain-level site hosting.

### Ownership and Management

Sites exist as on-chain objects that can be transferred between users like any other blockchain asset. While sites do not support direct upgrades, they can be replaced with newer versions under different identifiers. The system supports collaborative ownership, meaning multiple accounts can co-manage a site through smart contract permissions.

### MySocial Integration

Sites can embed MyIP media directly, ensuring decentralized content distribution throughout the user experience. Smart contracts enable dynamic functionality such as user authentication, content gating, and monetization using MySo tokens. Personalized sites can be automatically generated for NFTs, MySocial profiles, or other blockchain-linked assets.

All hosting fees, storage costs, and related transactions are processed exclusively in MySo tokens, ensuring tight integration with the MySocial ecosystem and eliminating dependencies on external payment systems or tokens.