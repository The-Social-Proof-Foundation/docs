---
icon: magnifying-glass
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

# Content Analysis & Oracle System

The Proof of Creativity content analysis system uses an oracle-based approach to automatically detect content similarity and determine originality. This system is the foundation of MySocial's content ownership protection, ensuring creators receive proper attribution and compensation.

## Oracle Architecture

The oracle service is built with FastAPI and Python 3.11+, deployed with Docker, and supports both Google Cloud Storage and Walrus decentralized storage. It uses Timescale Vector AI for high-performance vector similarity search and can process content in real time using HNSW vector indexes.

The oracle analyzes content when media files are uploaded, when smart contracts call for verification, or during batch processing of historical content.

## Advanced Similarity Detection

The system uses specialized algorithms for each media type:
- **Images:** CLIP embeddings and vector similarity in 512-dimensional space, with advanced fingerprinting and real-time processing (~100 images/second).
- **Videos:** Keyframe analysis at 1 fps, combined visual and audio analysis, batch processing up to 300 frames per video, and dual detection for both image and audio (~10 videos/second).
- **Audio:** Shazam-style fingerprinting, constellation mapping, robust hash generation, and time offset clustering (~50 audio files/second).

## API Processing Flow

Content is uploaded to the oracle API, which processes the file, generates embeddings or fingerprints, performs vector search, and returns similarity results. The oracle then calls the blockchain smart contract to submit analysis results. Example upload:

```bash
curl -X POST "http://localhost:8000/upload" \
  -H "accept: application/json" \
  -H "Content-Type: multipart/form-data" \
  -F "file=@your-image.jpg"
```

## Similarity Scoring & Confidence Levels

The oracle uses confidence-based thresholds:
- High confidence: ≥ 0.9 similarity score
- Medium confidence: ≥ 0.7 similarity score
- Low confidence: < 0.7 similarity score

The default smart contract threshold is 95% for all media types, configurable by governance. Content below the threshold is considered original; above the threshold, it is considered derivative and subject to revenue redirection.

## Revenue Redirection Calculation

When similarity exceeds the threshold, the system calculates the redirection percentage using:

```
Delta = (Similarity Score - Threshold) / (100 - Threshold)
Redirect Percentage = (Base Redirect % × Delta) / 100
```

For example, a similarity score of 98% with a 95% threshold and 100% base redirect results in a 60% redirect.

## Oracle Response Flow

After analysis, the oracle updates the post with the PoC result, synchronizes token pools, and emits events for transparency. Errors are handled for invalid media types, unauthorized oracles, missing original creators, and invalid thresholds.

## Integration Points

PoC analysis is automatically triggered when posts are created, with results stored in post objects and reflected in token pools. The event system provides transparency and audit trails for all decisions.

## Oracle Security & Trust

The oracle operates as a single authority with admin oversight, upgradeability, and public logging. Future enhancements may include multi-oracle support, consensus mechanisms, decentralized analysis nodes, and automated appeals.

The content analysis system provides the technical foundation for fair content attribution, ensuring original creators are protected while maintaining a transparent and auditable process for all PoC determinations.
