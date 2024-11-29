# 🗒️ EAS and Resolvers

### Overview

The project utilizes the Ethereum Attestation Service (EAS) to create a web of trust system through two main schemas:

* Pretrust Schema
* Vouch Schema

### Schemas

#### Pretrust Schema

The pretrust schema serves as the seeding group for the web of trust. Its primary purpose is to ensure that each unique Zupass credential is linked to only one Ethereum address.

**Schema Structure:**

```solidity
bytes32 nullifier,
bytes32 category,
bytes32 subcategory,
bytes32 issuer,
bytes32 credentialType,
bytes32 platform
```

**Schema URL:** [Base EAS Scanner - Pretrust Schema](https://base.easscan.org/schema/view/0xe6428e26d2e2c1a92ac3f5b30014a228940017aa3e621e9f16f02f0ecb748de9)

**Pretrust Resolver**

The pretrust resolver implements the following key functionality:

* Validates Zupass credentials
* Ensures one-to-one mapping between credentials and addresses
* Prevents duplicate attestations for the same credential

#### Vouch Schema

The vouch schema represents endorsements between users within the system.

**Schema Structure:**

```solidity
bytes32 platform,
bytes32 category,
bytes32 subCategory
```

**Schema URL:** [Base EAS Scanner - Vouch Schema](https://base.easscan.org/schema/view/0xb6b4f5642693a970d1c43bfd55b34a6a32cdce692c390958f201a5f529eb6893)

**Vouch Resolver**

The vouch resolver provides the following capabilities:

* Season management by admins
* Vouch limit enforcement per user per season
* Admin management system
* Query interface for season and user data

### Base Sepolia

[Vouch Resolver Contract ](https://sepolia.basescan.org/address/0x000000abc3f5670c699c40bf8aedb99a145524ae#readContract)

[Vouch Schema](https://base-sepolia.easscan.org/schema/view/0xa142412d946732a5a336236267a625ab2bc5c51b9d6f0703317bc979432ced66)



### Add new Communities and/or Categories

Currently, you need to be whitelisted for this. Join this telegram group for requests: [https://t.me/+BEa8nA1BW-swMzk5](https://t.me/+BEa8nA1BW-swMzk5)&#x20;

1. Head to Resolver Contract
2. Go to `Read Contract` and then to `getVouchCode`
3. Go to `Write Contract` and then fill the Code you got from previous step in `setVouchingLimit`&#x20;



