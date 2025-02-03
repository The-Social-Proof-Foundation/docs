---
icon: fingerprint
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

# zkLogin

zkLogin enables users to perform actions on MySocial by leveraging familiar OAuth login flows, such as those from providers like Google, Facebook, or Apple. This approach eliminates the need for users to manage separate cryptographic keys or remember complex mnemonics. Instead, users can authenticate using their existing accounts, and zkLogin ensures that their on-chain activities remain unlinkable to their off-chain identities through the use of zero-knowledge proofs.

How zkLogin Works
1.	**OAuth Authentication and JWT Acquisition**
The process begins with the user initiating an OAuth login with a supported provider. Upon successful authentication, the provider issues a JSON Web Token (JWT), which includes a nonce—a unique value that, in this context, is defined as an ephemeral public key and an expiry epoch. This nonce ensures the freshness and uniqueness of the authentication session.
2.	**Ephemeral Key Pair Generation**
Simultaneously, the user’s wallet application generates an ephemeral key pair. The public part of this key pair is embedded in the nonce within the JWT. The corresponding private key is used to sign transactions during this session, providing a layer of security without requiring long-term key storage.
3.	**Zero-Knowledge Proof Generation**
To maintain privacy, zkLogin employs the Groth16 zero-knowledge proof system. The wallet uses the JWT to generate a zero-knowledge proof that attests to the validity of the user’s authentication without revealing sensitive information. This proof ensures that the user’s OAuth credentials are valid and that the user controls the associated ephemeral private key, all without exposing any identifying details.
4.	**Transaction Submission**
When the user initiates a transaction on MySocial, the wallet signs the transaction using the ephemeral private key and attaches the zero-knowledge proof. This composite transaction is then submitted to the MySocial network.
5.	**Verification and Execution**
Upon receiving the transaction, MySocial’s validators verify both the ephemeral signature and the zero-knowledge proof. If both are valid, the transaction is executed, and its effects are recorded on the blockchain. Notably, the user’s on-chain address is derived from the OAuth provider’s identifier (iss), the user’s unique subject identifier (sub), the audience (aud), and a user-specific salt. This derivation ensures that the on-chain address cannot be linked back to the user’s OAuth identity, preserving privacy.

## Technical Details

• **Zero-Knowledge Proofs (ZKPs):** zkLogin utilizes the Groth16 zkSNARK protocol, which requires a one-time setup to generate a common reference string (CRS). This CRS is used to produce the proving and verifying keys necessary for generating and validating proofs. The proving key is employed by the wallet to create proofs, while the verifying key is used by MySocial’s validators to confirm their validity.
•	**Ephemeral Keys and Nonces:** The use of ephemeral key pairs enhances security by limiting the lifespan of cryptographic keys. Embedding the ephemeral public key in the JWT’s nonce field ties the authentication session to a specific key pair, ensuring that each session is unique and reducing the risk of key compromise.
•	**Address Derivation:** The user’s on-chain address is computed using a combination of the OAuth provider’s identifier (iss), the user’s subject identifier (sub), the audience (aud), and a user-specific salt. This method ensures that the address is unique to the user and their chosen provider, while the inclusion of the salt prevents any potential linkage between the user’s on-chain and off-chain identities.

## Security and Privacy Considerations

zkLogin is designed with a strong emphasis on security and privacy:
**•	Self-Custody:** Users retain full control over their assets, as transactions require explicit approval through their OAuth login and the possession of the ephemeral private key.
**•	Two-Factor Authentication:** The combination of the OAuth credential and the ephemeral private key acts as a form of two-factor authentication, enhancing security by requiring two independent factors for transaction authorization.
**•	Privacy Preservation:** Zero-knowledge proofs ensure that while validators can confirm the validity of a transaction, they gain no knowledge of the user’s off-chain identity, maintaining confidentiality.

By integrating zkLogin, MySocial offers a seamless and secure authentication experience, allowing users to interact with the platform using their existing credentials while ensuring that their privacy is rigorously protected.