---
icon: link
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

MySocial is a Layer 1 blockchain optimized for SocialFi and InfoFi applications, enabling fast, low-cost transactions and empowering users with true ownership of their content, social connections, and data. The platform is designed not only for social interactions but also to support a robust data marketplace, allowing users to monetize and control access to their information. Built on top of the Move Virtual Machine, MySocial leverages parallel transaction execution, object-based data storage, and the Move programming language—to deliver a highly scalable and developer-friendly environment for social and data-driven applications.

## The MySocial Blockchain
MySocial operates independently with its own consensus mechanism, validator network, and native token. Unlike traditional social media platforms that rely on centralized servers to store and control user data, MySocial ensures that all interactions, content, and relationships are recorded on-chain. This approach guarantees censorship resistance, data portability, and true content ownership. The integrated data marketplace (InfoFi) further enables users to participate in a new economy where information is a first-class asset.

In comparison, Layer 2 blockchains build on top of existing Layer 1 infrastructures, leveraging their security while introducing scalability enhancements. Since MySocial is its own Layer 1 blockchain, it maintains full sovereignty over its protocol and governance, allowing for innovations tailored specifically to the needs of SocialFi and InfoFi applications.

Unlike general-purpose blockchains that allow arbitrary smart contract deployment, MySocial does not permit direct smart contract publishing. Instead, developers interact with the blockchain through dedicated endpoints, APIs, and SDKs. This ensures a streamlined and optimized experience for social and data marketplace applications while maintaining security and efficiency. By focusing on structured interactions rather than open-ended execution, MySocial provides a developer-friendly environment that prioritizes scalability, usability, and seamless integration with social and data-driven experiences.

## Core Architecture
Consensus Mechanism: Narwhal and Bullshark (DAG-based DPoS)

MySocial utilizes a high-throughput DAG-based consensus architecture composed of two distinct layers: Narwhal and Bullshark. Narwhal serves as the transaction dissemination and data availability layer, ensuring reliable propagation and cryptographic storage of transaction certificates across the validator set. Built ontop Narwhal, Bullshark acts as the consensus engine, sequencing certificates into a globally agreed ledger under a Byzantine fault-tolerant protocol. This separation between data availability and consensus ordering enables parallelism, scalability, and low-latency finality, even under adversarial conditions. Bullshark guarantees both safety and liveness under partial synchrony, tolerating up to one-third of Byzantine validators.

The execution model distinguishes between transactions involving exclusively owned or read-only objects (which can bypass full consensus for lower latency) and those involving shared objects (which require global ordering through Bullshark). This hybrid approach minimizes coordination overhead and enables high throughput, supporting the demands of SocialFi and InfoFi use cases.

Validators on the MySocial network must stake MySo to participate in consensus and process transactions. Users can also delegate their MySo to trusted validators, contributing to the network's security while earning staking rewards. DPoS aligns the incentives of validators and users, ensuring MySocial remains fast, secure, and efficient without the high energy costs associated with older blockchain models.

## Network Infrastructure
#### Mainnet
The primary network where real-world transactions occur. This is the production environment where users, creators, and developers interact with live applications.

#### Testnet
A public staging network where developers can test updates and improvements before deploying to Mainnet. This ensures stability and security for all MySocial applications.

#### Localnet
Developers can run a private MySocial network on their local machine to streamline the development process without needing an external network connection.

## Move Programming Language
MySocial leverages Move, a powerful and flexible smart contract language originally developed by Meta (formerly Facebook) for the Diem blockchain project. Move provides a secure and efficient framework for handling on-chain assets, such as NFTs, user identities, social graphs, and data marketplace objects.

Unlike traditional smart contract languages that rely on account-based models, Move utilizes an object-based model, allowing for greater control and composability of digital assets and data. This is particularly beneficial for SocialFi and InfoFi applications, where dynamic interactions between users, content, and data require more flexibility than traditional blockchain architectures provide.

## Conclusion
MySocial is designed to bring true ownership and freedom to social media and data economies by leveraging blockchain technology in a way that is efficient, scalable, and developer-friendly. Whether you're a creator, user, or developer, MySocial offers the tools and infrastructure you need to build the future of digital and data-driven interactions. 🚀
