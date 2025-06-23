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

The Proof of Creativity content analysis system uses an **oracle-based approach** to automatically detect content similarity and determine originality. This system is the foundation of MySocial's content ownership protection, ensuring creators receive proper attribution and compensation.

## Oracle Architecture

### FastAPI-Based Oracle Service
- **Production-Ready API**: Built with FastAPI and Python 3.11+
- **Scalable Infrastructure**: Docker deployment with health monitoring
- **Multi-Backend Storage**: Supports Google Cloud Storage and Walrus decentralized storage
- **Timescale Vector AI**: High-performance vector database for similarity search
- **Real-time Processing**: Sub-second analysis with HNSW vector indexes

### Analysis Trigger
The oracle analyzes content when:
- Media files are uploaded via `/upload` endpoint
- Blockchain smart contract calls oracle for content verification
- Batch processing of historical content for similarity detection

## Advanced Similarity Detection

### Multi-Modal Processing Pipeline
The system uses different specialized algorithms for each media type:

**Images (Type 1)**
- **CLIP Embeddings**: OpenAI CLIP model for visual content understanding
- **Vector Similarity**: Cosine similarity search in 512-dimensional space
- **Perceptual Features**: Advanced image fingerprinting beyond simple hashing
- **Real-time Processing**: ~100 images/second throughput

**Videos (Type 2)**  
- **Frame Extraction**: Keyframe analysis at 1 fps (configurable)
- **Combined Analysis**: Both visual frames and audio track processing
- **Batch Processing**: Up to 300 frames per video (10 minutes max)
- **Dual Detection**: Leverages both image and audio algorithms
- **Performance**: ~10 videos/second processing rate

**Audio (Type 3)**
- **Shazam-Style Fingerprinting**: Spectral peak pair hashing algorithm
- **Constellation Mapping**: Time-frequency peak coordinate analysis
- **Hash Generation**: Frequency pair + time delta robust matching
- **Time Offset Clustering**: Handles speed variations and noise
- **Performance**: ~50 audio files/second processing rate

### Timescale Vector AI Integration

The system leverages cutting-edge vector database technology:

```sql
-- HNSW index for sub-second vector search
CREATE INDEX idx_media_embeddings_vector_hnsw 
ON media_embeddings USING hnsw (embedding vector_cosine_ops) 
WITH (m = 16, ef_construction = 64);

-- Time-series + vector filtering for similarity search
SELECT media_id, (1 - (embedding <=> $1)) as similarity_score
FROM media_embeddings
WHERE uploaded_at > NOW() - INTERVAL '24 hours'
  AND (1 - (embedding <=> $1)) >= 0.8
ORDER BY embedding <=> $1
LIMIT 10;
```

**Performance Benchmarks:**
- **1M vectors**: < 10ms average query time
- **10M vectors**: < 50ms average query time  
- **HNSW index**: 95%+ recall with 10x speed improvement

### API Processing Flow

**Upload and Analysis Endpoint:**
```bash
curl -X POST "http://localhost:8000/upload" \
  -H "accept: application/json" \
  -H "Content-Type: multipart/form-data" \
  -F "file=@your-image.jpg"
```

**Response Format:**
```json
{
  "media_id": "123e4567-e89b-12d3-a456-426614174000",
  "filename": "example.jpg",
  "content_type": "image/jpeg",
  "file_size": 2048576,
  "file_hash": "a1b2c3d4...",
  "storage_uri": "gs://bucket/path/file.jpg",
  "matches": [
    {
      "media_id": "other-media-id",
      "similarity_score": 0.95,
      "match_type": "embedding",
      "confidence_level": "high"
    }
  ],
  "processing_status": "completed",
  "message": "Found 1 high-confidence match - possible derivative content"
}
```

**Smart Contract Integration:**
The oracle calls `analyze_and_update_post` to submit analysis results to the blockchain.

The complete processing pipeline:
1. **Media Upload**: File uploaded to oracle API endpoint
2. **Content Processing**: CLIP embeddings or audio fingerprints generated
3. **Vector Search**: Timescale Vector AI performs similarity search
4. **Match Analysis**: Results analyzed for confidence and threshold comparison
5. **Blockchain Submission**: Oracle calls smart contract with similarity results
6. **PoC Decision**: Smart contract determines badge issuance or revenue redirection

## Similarity Scoring & Confidence Levels

### Confidence-Based Threshold System
The oracle uses sophisticated confidence scoring rather than simple thresholds:

**Confidence Levels:**
- **High Confidence**: ≥ 0.9 similarity score (90%+)
- **Medium Confidence**: ≥ 0.7 similarity score (70%-89%)
- **Low Confidence**: < 0.7 similarity score (Below 70%)

**Smart Contract Thresholds:**
- **Default Threshold**: 95% for all media types (configurable by governance)
- **Percentage Based**: Thresholds expressed as percentages (0-100)
- **Governance Control**: Community can adjust thresholds through voting
- **Media-Specific**: Different thresholds can be set per media type

### Score Interpretation
- **Below Threshold**: Content considered original → PoC badge issued
- **Above Threshold**: Content considered derivative → Revenue redirection applied
- **Confidence Matching**: Oracle confidence level must align with smart contract decision

## Revenue Redirection Calculation

When similarity exceeds threshold, the system calculates redirection percentage:

```
Delta = (Similarity Score - Threshold) / (100 - Threshold)
Redirect Percentage = (Base Redirect % × Delta) / 100
```

**Example Calculation:**
- Similarity Score: 98%
- Threshold: 95%
- Base Redirect: 100%
- Delta: (98-95)/(100-95) = 3/5 = 60%
- Final Redirect: (100 × 60)/100 = 60%

This formula ensures:
- **Gradual Scaling**: Higher similarity = higher redirection
- **Fair Attribution**: Proportional compensation to original creator
- **Threshold Sensitivity**: Small differences have meaningful impact

## Oracle Response Flow

### Successful Analysis
1. **Content Processed**: Oracle analyzes submitted content
2. **Score Generated**: Similarity percentage calculated
3. **Decision Applied**: Badge or redirection based on threshold
4. **Post Updated**: PoC result stored in post data
5. **Token Sync**: Social Proof Token pools automatically updated
6. **Event Emitted**: Analysis result broadcasted to network

### Error Handling
- **Invalid Media Type**: Analysis rejected with error
- **Unauthorized Oracle**: Only configured oracle can submit results
- **Missing Original Creator**: Redirection requires valid creator address
- **Threshold Validation**: Ensures thresholds are within valid ranges

## Integration Points

### Post System Integration
- **Automatic Triggering**: Analysis happens when posts are created
- **Data Storage**: PoC results stored directly in post objects
- **Status Updates**: Posts reflect PoC badges or redirection status

### Token Pool Synchronization
- **Real-time Updates**: Token pools immediately reflect PoC decisions
- **Revenue Routing**: Future token sales respect redirection rules
- **Pool Metadata**: PoC status visible in token pool information

### Event System
- **Analysis Events**: Detailed logs of all oracle decisions
- **Transparency**: Public visibility of similarity scores and decisions
- **Audit Trail**: Complete history of PoC determinations

## Oracle Security & Trust

### Authorization Model
- **Single Authority**: Reduces complexity and potential conflicts
- **Admin Oversight**: Oracle address controlled by system administrators
- **Upgradeable**: Oracle can be replaced if needed
- **Accountability**: All oracle actions are publicly logged

### Future Enhancements
- **Multi-Oracle Support**: Potential for multiple oracle validation
- **Consensus Mechanisms**: Cross-validation of analysis results
- **Decentralized Oracles**: Community-operated analysis nodes
- **Appeal Processes**: Automated review of disputed decisions

The content analysis system provides the technical foundation for fair content attribution, ensuring original creators are protected while maintaining a transparent and auditable process for all PoC determinations. 