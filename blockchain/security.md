---
icon: lock
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

# Security

At MySocial, we prioritize the security of our users’ data and assets, ensuring a safe and trustworthy platform for social interactions. Our comprehensive security framework is designed to protect user information, maintain data integrity, and uphold privacy.

## Security Features

MySocial employs advanced security measures to safeguard user assets and data. Each asset is associated with a unique identifier and is accessible only by its owner through a private cryptographic key. This ensures that only the rightful owner can authorize transactions involving their assets. Additionally, our platform utilizes smart contracts written in the Move programming language, which define the rules for asset interactions. These contracts are auditable, allowing for transparency and verification of the predefined logic governing asset usage.

## Security Architecture

Our platform operates on a decentralized network of independent validators that process transactions and maintain the system’s integrity. We implement Byzantine Fault Tolerant (BFT) consensus protocols, enabling the network to function correctly even if a subset of validators behaves maliciously or encounters failures. Each validator’s voting power is determined through a staking mechanism, where users delegate their tokens to support chosen validators. As long as more than two-thirds of the total stake is held by honest validators, the network remains secure and reliable.

## Your Control Over Your Assets

Users have exclusive control over their assets on MySocial. A transaction is considered valid only if it is digitally signed by the asset owner’s private key, which should be kept confidential. This mechanism ensures that no other party can operate on a user’s owned asset without detection, even if some validators fail to follow the protocol. Users can manage multiple addresses corresponding to different signature keys for convenience or privacy purposes. It’s important to verify recipient addresses during transfers, as sending assets to an incorrect address may result in irreversible loss.

## Transaction Finality

Our platform ensures that once a transaction is validated and finalized, its effects are permanently recorded on the blockchain, making them immutable and available for future operations. This permanence guarantees that your data remains consistent and reliable across the network.

Our system is designed to handle scenarios where some validators may not adhere to the protocol. Even in such cases, transactions can still be finalized through the consensus of the honest validators. This resilience is achieved through the use of cryptographic Byzantine fault-tolerant agreement protocols, which ensure that incorrect validators cannot mislead the system or prevent transaction processing.

To prevent denial-of-service attacks and ensure efficient processing, all transactions on MySocial are associated with a gas fee. A valid transaction may either execute successfully or abort due to conditions within the smart contract or insufficient gas. In both scenarios, the gas fee is charged accordingly, maintaining the system’s overall health and performance.

Users have the flexibility to submit transactions and their certificates directly or through trusted third-party services. These third parties do not have access to your private keys and cannot forge transactions on your behalf. They can, however, provide confirmation of a transaction’s finality through validator signatures, ensuring that once a transaction is finalized, its effects are permanent and reliable.

## Auditing and Privacy

All operations on MySocial are transparent and can be audited to verify correct processing. This transparency allows users to trace the history of their assets and ensures accountability. However, since all operations are publicly visible, users concerned about privacy may opt to use multiple addresses to maintain pseudonymity. Additionally, specific smart contracts with enhanced cryptographic privacy protections can be utilized to further safeguard user information.

## Censorship-Resistance and Openness

MySocial employs a Delegated Proof-of-Stake model to periodically determine its set of validators. Users can lock and delegate their tokens to support one or more validators, influencing the composition of the validator committee. This mechanism ensures that validators are accountable to users and can be replaced in cases of unreliability or misbehavior, including attempts to censor valid transactions. Through their choice of validators and the protocols they support, users have a meaningful say in the future evolution of the MySocial system.

By implementing these robust security measures, MySocial ensures a secure and reliable environment for all users, allowing them to engage confidently on our platform.