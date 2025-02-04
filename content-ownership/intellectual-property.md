---
icon: copyright
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

# Intellectual Property

MySocial is built on the idea that content creators should fully own their work. Unlike traditional social media platforms where content rights are often transferred to the platform itself, MySocial ensures that users maintain full control over their creative work. This system ensures that videos, photos, articles, and other digital assets belong to their creators, allowing them to earn money from their content.

## On-Chain IP Registration System

To prove ownership and control monetization, MySocial offers a decentralized IP registration system. This system lets creators officially register their content on the MySocial blockchain, ensuring it is safe and verifiable.

### MySocial IP Address (MyIP)

Every registered piece of content receives a unique **MySocial IP address (MyIP)**, which acts like a digital certificate proving ownership.

* The MyIP is stored permanently on the blockchain and linked to the creator’s profile.
* It follows the **MyIP Metadata Standard**, which includes important details like the creation date, owner information, content type, and licensing rules.
* Once registered, the IP cannot be changed, deleted, or claimed by someone else unless the owner transfers it.

## Monetization and Content Protection

By registering content with MySocial, creators gain exclusive rights to:

* **License** and sell their content, allowing them to earn revenue.
* Earn **royalties** through smart contracts, ensuring they get paid automatically when their content is used or resold.

Protect against content theft, since ownership is permanently recorded on the blockchain, making disputes easier to resolve.

## Blockchain-Powered Licensing with NFT-Like Objects

MySocial enhances content ownership with NFT-like objects, offering advanced digital rights management:

* MySocial uses the Move programming language, where content acts as independent objects that can be bought, sold, or transferred just like NFTs.
* Creators can turn their content into NFT-like objects, which serve as digital proof of ownership.
* Smart contracts allow creators to set licensing rules, automate royalty payments, and control content distribution.
* Businesses and individuals can easily purchase, rent, or license content on the blockchain, ensuring fairness and transparency.

## Compatibility and Cross-Platform Use

The MySocial Metadata Standard is designed for seamless integration with other platforms, ensuring:

* Easy compatibility with other blockchain marketplaces and apps.
* Recognition of MySocial-registered IP across multiple networks.

The ability to move content across different Web3 platforms while retaining ownership and rights.

## Conclusion

MySocial’s blockchain-based IP system gives creators full control over their content, allowing them to own, protect, and monetize their work without relying on middlemen. By providing unique MyIP addresses, structured metadata, and smart contract-driven licensing, MySocial sets a new standard for digital content ownership in the social media space.





```
{
  "title": "MyIP Metadata Standard",
  "description": "Metadata schema for intellectual property registered on MySocial blockchain.",
  "type": "object",
  "properties": {
    "myip_id": {
      "type": "string",
      "description": "Unique MyIP identifier assigned to the content."
    },
    "title": {
      "type": "string",
      "description": "Title of the content."
    },
    "creator": {
      "type": "string",
      "description": "Blockchain address or identity of the original creator."
    },
    "creation_date": {
      "type": "string",
      "format": "date-time",
      "description": "ISO 8601 timestamp marking the content’s creation."
    },
    "content_type": {
      "type": "string",
      "enum": ["video", "image", "audio", "text", "other"],
      "description": "Type of digital content."
    },
    "license": {
      "type": "string",
      "description": "License type governing content usage and rights."
    },
    "hash": {
      "type": "string",
      "description": "Cryptographic hash of the content to verify integrity."
    },
    "storage_uri": {
      "type": "string",
      "description": "Decentralized storage link (e.g., IPFS, Arweave) to access content."
    },
    "royalty_percentage": {
      "type": "number",
      "minimum": 0,
      "maximum": 100,
      "description": "Royalty percentage for resale or licensing."
    },
    "transferable": {
      "type": "boolean",
      "description": "Indicates if the ownership of the content is transferable."
    },
    "owners": {
      "type": "array",
      "items": {
        "type": "string",
        "description": "List of current owner addresses."
      }
    },
    "history": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "event": { "type": "string", "description": "Event type (e.g., creation, transfer, license)." },
          "timestamp": { "type": "string", "format": "date-time", "description": "Time of the event." },
          "transaction_hash": { "type": "string", "description": "Transaction hash for verification." },
          "involved_parties": { "type": "array", "items": { "type": "string" }, "description": "List of parties involved in the event." }
        },
        "description": "History of significant events related to this IP."
      }
    }
  },
  "required": ["myip_id", "title", "creator", "creation_date", "content_type", "hash", "storage_uri"]
}

```
