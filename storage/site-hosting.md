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

{% hint style="info" %}
Content will be available shortly. Please check back soon!
{% endhint %}

Support subscription models for media: Creators can store encrypted media on Walrus and only provide access via decryption keys to parties that have paid a subscription fee or have paid for content. Walrus provides the storage, encryption, and decryption needs to happen off the system.

Support a fully decentralized web experience: Walrus can host fully decentralized web experiences, including all resources (such as js, css, html, and media). These can not only provide content but also host the UX of dApps to enable applications with fully decentralized front end and back ends on chain. Walrus puts the full "web" into web3.

https://github.com/MystenLabs/walrus-docs/blob/main/docs/walrus-sites/intro.md

https://walrus.site/

\*\* They are not upgradeable


MySocial **Site Hosting** allows users to deploy fully decentralized websites using the same principles as **MyIP and blob-based storage**. This system eliminates the need for traditional web hosting infrastructure by leveraging MySocial’s **storage layer**. Developers and creators can seamlessly publish, update, and exchange websites, making them censorship-resistant and persistently available.

Sites hosted on MySocial function similarly to traditional static websites but are **distributed, verifiable, and tamper-proof**. They can be associated with **a MySocial namespace or the creator’s username**, offering a human-readable domain option for easy accessibility.

## Features of MySocial Site Hosting

- **No Servers Required**: Just upload your site’s source files, and MySocial will handle storage and retrieval.
- **Domain Customization**: Use your **MySocial username** or a generated content-based subdomain.
- **Immutable & Updatable**: Sites are stored as **on-chain objects** and can be transferred between owners, but they are **not upgradeable**.
- **Censorship Resistance**: No central authority can take down your website.
- **Integration with MySocial Identity**: Sites can link directly to MyIP content, profiles, and MySocial assets.
- **Support for Subscription Models**: Creators can store encrypted media and provide decryption keys only to paid subscribers or users who purchase content. While MySocial provides the storage, decryption must happen off-system.
- **Fully Decentralized Web Experiences**: MySocial Site Hosting enables fully decentralized websites, including all required resources (such as JS, CSS, HTML, and media). This allows dApps to have both decentralized frontends and backends.

## Technical Overview

### **Decentralized Storage & Retrieval**

All MySocial-hosted sites are stored using **blob-based decentralized storage**, ensuring that:
- Files are **fragmented and distributed** across multiple nodes for redundancy.
- Data retrieval is **optimized using Content Addressable Storage (CAS)**.
- Availability is maintained through **storage proofs and incentivized retrieval mechanisms**.

When a user visits a MySocial-hosted site, the browser retrieves metadata from the blockchain and fetches the necessary assets from the storage network.

### **How Sites Are Accessed**

MySocial Site Hosting operates on a subdomain system, where:
- **MySocial usernames** can be used as human-readable domain names (e.g., `yourname.mysocial.site`).
- **Base36 Encoded Object IDs** serve as unique identifiers for site retrieval (e.g., `abcdef123456.mysocial.site`).
- **Custom Namespaces** allow for personal branding and domain-level site hosting.

### **Updatability & Ownership**

Since sites exist as **on-chain objects**, they:
- Can be **transferred between users** like any other blockchain asset.
- Do **not support direct upgrades** but can be replaced with newer versions under a different identifier.
- Allow for **collaborative ownership**, meaning multiple accounts can co-manage a site.

### **Integration with MySocial Content**

- Sites can embed **MyIP media** directly, ensuring decentralized content distribution.
- Smart contracts enable dynamic functionality such as user authentication, content gating, and monetization.
- Personalized sites can be automatically generated for NFTs, MySocial profiles, or other blockchain-linked assets.