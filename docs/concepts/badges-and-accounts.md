# Accounts & Badges: The Subjective Map

Badges form the core identity primitive of the Web3 Outpost. Attached to sybil-resistant accounts, badges differentiate users over time by recording verifiable history, roles, characteristics, and contributions.

---

## Accounts

All participants in the Society Protocol movement create an Ethereum-based account within the Web3 Outpost.

- **Long-Term Continuity:** Users are encouraged to maintain a single main account that accumulates a rich, multi-year history.
- **Referral Chains:** Accounts support permanent referral chains, recording relationships between participants that can later inform Genesis parameters in Web4 SP instances.

## Badges (ERC-1155)

Badges are non-fungible or semi-fungible tokens minted to accounts. They serve two primary roles:

1. **Functional Credentials:** Unlock token-gated communication channels, DAO governance rights, or administrative moderation roles.
2. **Permanent Attributions:** Create verifiable proof of event attendance, core contributions, or verified off-chain attributes (via zkTLS).

---

## Technical Architecture

Badges leverage **ERC-1155** on Ethereum Mainnet for gas efficiency and modularity. 

```text
+-------------------+      zkTLS / SPEC Lock      +--------------------+
|                   |  ------------------------>  |                    |
|   User Account    |                             | SingleMintHook     |
|   (Web3 Outpost)  |  <------------------------  | Verification       |
+-------------------+       Mint Token ID         +--------------------+
                                                            |
                                                            v
                                                  +--------------------+
                                                  |  ERC-1155 Badge    |
                                                  |  (Society Protocol)|
                                                  +--------------------+
```

### Core Token Properties

| Property | Value / Description |
| :--- | :--- |
| **Token Standard** | ERC-1155 Multi-Token |
| **Proxy Contract** | See [Smart Contracts Reference](../technical/contracts.md) |
| **Implementation** | See [Smart Contracts Reference](../technical/contracts.md) |
| **Mint Enforcer** | `SingleMintHook` (verifies zkTLS proofs and SPEC locks) |
| **URI Scheme** | `ipfs://` metadata resolved via protocol registry |
