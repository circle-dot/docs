# Getting Rank Scores

[GitHub Repository](https://github.com/circle-dot/eigenscore)

### Overview

EigenScore is a trust scoring system that leverages the OpenRank EigenScore algorithm to calculate reputation within specific communities based on attestations and interactions.

### Trust Score Calculation

#### Core Components

**1. Attestation-Based Trust**

* Scores are derived from attestations between community members
* Each attestation represents a trust relationship between:
  * Attester (source of trust)
  * Recipient (destination of trust)

**2. Pretrust Mechanism**

* Designated addresses serve as trust anchors
* These addresses have higher weight in calculations
* Help bootstrap the trust network

**3. Local Trust Network**

* Built from direct attestations between members
* Each attestation carries a base value of 1 (by default)
* Excludes self-attestations
* Forms the primary trust graph

#### Calculation Process

1. **Data Collection**
   * Fetches attestations from specified schemas
   * Filters relevant trust relationships
   * Builds local trust network
2. **Trust Propagation**
   * Uses EigenTrust algorithm
   * Iteratively propagates trust through network
   * Converges to stable trust scores
3. **Score Normalization**
   * Final scores are normalized
   * Ranked relative to community
   * Stored with position tracking

### Implementation Notes

* Scores update periodically via cronjob
* Supports multiple community configurations
* Includes sybil resistance measures
* Real-time score querying available

### Limitations

* Requires active attestation network
* Trust anchors (pretrust) influence heavily
* Score quality depends on network size
* Only considers on-chain attestations

### Security Considerations

* Protected API endpoints
* Origin verification
* Rate limiting
* Attestation validation
