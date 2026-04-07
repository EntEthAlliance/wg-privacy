# EEA Privacy Report — Full Content for Web Design

## Document Info
- Title: "State of Privacy on Ethereum for Enterprise"
- Subtitle: "Mapping Financial Institution Requirements to Ethereum Solutions"
- Organization: Enterprise Ethereum Alliance — Privacy Working Group
- Date: March 2026
- Status: DRAFT — For Working Group Only

## Opening Statement: The Principle of Collaborative Neutrality

This report represents a collective effort by the Enterprise Ethereum Alliance (EEA) Privacy Working Group to map the current landscape of privacy within the Ethereum ecosystem. From its inception, this report has been guided by neutrality as a core design principle. Our aim is to provide an objective, technical, and strategic framework for understanding how privacy is being integrated into enterprise-grade blockchain solutions.

The scope of this report is intentionally focused on the privacy solutions developed and maintained by EEA member organizations. By concentrating on the innovations within our ecosystem, we can ensure that solution characteristics are supported by live pilots, peer-reviewed empirical papers or enterprise deployments.

While we recognize the broader ecosystem of privacy research, deep-dives into non-member solutions fall outside the primary scope of this mandate. However, in the interest of authenticity and inclusivity, a comprehensive taxonomy of non-member solutions and academic primitives can be found in the 'Additional Privacy Solutions' section at the conclusion of this paper.

## Executive Summary

Financial institutions are increasingly deploying tokenized assets on Ethereum. However, on public blockchains, all transaction data is visible by default. Transaction amounts, counterparty identities, and business relationships are exposed on infrastructure that anyone can monitor.

Privacy and confidentiality are the missing pieces for enterprise adoption.

To address this, the Enterprise Ethereum Alliance, the member-driven organization connecting Fortune 500 companies, financial institutions, and technology providers with the Ethereum ecosystem, convened this Privacy Working Group to map the current landscape.

Seven EEA member organizations contributed their solutions, creating the first comprehensive enterprise-focused view of privacy capabilities on Ethereum.

This paper is a practical guide for enterprises to evaluate privacy solutions in order to utilize them for their own application of tokenized assets. It is designed for CIOs, compliance officers, and digital asset leads who need to evaluate options and ask the right questions.

Privacy has various applications and implementations. Different solutions protect different aspects of operations. No single solution covers all requirements. This paper provides the framework to understand what exists, how each approach works, and what implementation requires, so institutions can make informed decisions for their specific needs.

## Research Methodology

The findings within this paper were developed within the EEA Privacy Working Group over a dedicated three-month intensive study period. The methodology relied on a synthesis of technical documentation, stress-testing results, and deployment post-mortems from the world's leading financial and cryptographic institutions.

The working group was led by a steering committee comprising:
- Applied Blockchain and their Silent Data team
- Consensys and Linea
- COTI
- EY and the Nightfall teams
- Kaleido
- Polygon
- ZKsync and Matter Labs

Our process involved cross-review of privacy primitives, and the consolidation of proprietary enterprise requirements into a unified set of standards for Ethereum-based privacy.

## Enterprise Privacy Problem: The Barriers to Public Blockchain

For enterprises, the transparency that defines public blockchains is a "double-edged sword." While it provides immutable trust, it simultaneously creates a critical confidentiality deficit. The primary issues include:

**Exposure of Business Logic:** On a public ledger, smart contract interactions can reveal sensitive business logic, trade secrets, and proprietary algorithms to competitors.

**Lack of Financial Discretion:** Publicly visible transaction amounts and wallet balances are incompatible with corporate treasury requirements and high-stakes financial maneuvers.

**Regulatory Non-Compliance:** Regulations such as GDPR and MiCA require strict controls over data access and the "right to be forgotten," which are fundamentally at odds with a permanent, public, transparent ledger.

**Impact on Financial Strategy:** Visibility into transaction flows allows for front-running and "MEV" (Maximal Extractable Value) exploitation, which erodes the profitability of institutional trading strategies and introduces unacceptable threat actors.

### Institutional Trust Requirements

Institutions require an infallible level of trust in their financial products and instruments. The option for confidentiality is a requisite to preserve this trust in the process of tokenized assets. Without robust privacy, the public blockchain remains a "read-only" experiment for the world's largest enterprises.

## Privacy Addressable Market

The transition of institutional assets to the blockchain represents a multi-trillion-dollar opportunity. Privacy is not just a feature, it is the key that unlocks these sectors:

**Global Finance (TradFi):** The total addressable market for private decentralized finance (DeFi) includes the $100T+ global bond market and the $600T derivatives market, both of which require strict transaction privacy.

**Supply Chain & Logistics:** Protecting the identity of suppliers and the pricing of raw materials is essential for maintaining competitive advantages in global trade.

**Healthcare & Data Sovereignty:** The secure, private exchange of patient records and genomic data requires a "Privacy-First" architecture to meet global compliance standards.

## Taxonomy of Privacy Approaches in the Ethereum Ecosystem

### The Technical Primitives

**Fully Homomorphic Encryption (FHE):** An emerging field that allows data to remain encrypted even while it is being processed, ensuring that sensitive information is never "unlocked" during computation.

**Garbled Circuits (GC):** Distributes computation across decentralized software, enabling any one individual or multiple parties to collectively compute over data while it remains encrypted; this ensures that sensitive information is never "decrypted".

**Multi-Party Computation (MPC):** Distributes a computation across multiple parties such that no single party can see the entire data set, preventing any single point of failure or data leak.

**Trusted Execution Environments (TEEs):** Uses a hardware-secured "enclave" within a processor to run computations in complete isolation, ensuring that sensitive data cannot be accessed or tampered with — even by the host system or platform operator.

**Zero-Knowledge Proofs (ZKPs):** A way for one party to prove to another that a statement is true without revealing any information beyond the validity of the statement itself (e.g., "I have enough funds," without showing the balance).

**Privacy Groups:** A closed group of participants executing a shared business logic and maintaining a privately replicated ledger, while maintaining a state transition history on the public ledger with commitments to enforce consistency among the private ledgers.

### Privacy-Related Ethereum Standards

**ERC-5564 (Stealth Addresses):** Enables senders to generate private addresses for recipients without prior interaction. Recipients use viewing keys to identify incoming transfers without revealing their identity to observers.

**ERC-6538 (Stealth Meta-Address Registry):** Provides a registry for stealth meta-addresses, enabling senders to discover recipients and generate stealth addresses without prior direct interaction. Complements ERC-5564.

**ERC-7984 (Confidential Fungible Token) [Draft]:** Defines an interface for tokens with confidential balances and transfer amounts. Technology-agnostic, supporting FHE, ZK proofs, TEEs, or other privacy mechanisms.

## The Ethereum Foundation's Privacy Roadmap

Three Tracks:

**1. Private Proving (Application Layer):** Enabling users to prove facts about themselves without revealing underlying data. Projects: Semaphore (anonymous group membership proofs), MACI (collusion-resistant private voting), zkPDF (proving on signed PDF), zkEmail (email-based attestations).

**2. Private Writes (Transaction Layer):** Enabling confidential actions on Ethereum mainnet. Developing infrastructure for private transfers, precompiles, reference implementations, tooling on SDK integrations for privacy-first wallets including private account recovery.

**3. Private Reads (Network Layer):** Tackles metadata leakage from reading state. Developing Private Information Retrieval (PIR). Target: major RPC providers, wallets, and block explorers offer privacy alternatives within 12 months.

## Trust Models of Enterprise Privacy Solutions

### Cryptographic Trust (ZK, MPC, Garbled Circuits)
- Trust placed in publicly verifiable cryptography, not any single operator
- ZK: Proofs are mathematically verifiable by anyone
- MPC & GC: Trust in protocol design and cryptographic primitives
- Failure modes: Circuit bugs, missing constraints, malicious inputs, incremental leakage

### Hardware-Anchored Trust (TEE)
- Trust placed in hardware security guarantees by manufacturers
- Relies on secure enclaves and remote attestation
- Failure modes: Attestation compromise, leaked encryption keys, side-channel attacks

### Organizational Honesty (FHE Co-Processors, MPC, Notary)
- Trust placed in honesty of organizations operating core components
- FHE: Majority of co-processor operators must be honest
- MPC: At least one honest party required
- Failure modes: Collusion above trust threshold enables full data reconstruction

## Privacy Coverage Matrix

| Capability | COTI | Linea Enterprise | Nightfall (EY) | Paladin (Kaleido) | Prividium (ZKsync) | Agglayer CDK (Polygon) | Silent Data |
|---|---|---|---|---|---|---|---|
| Transaction Privacy | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Balance Privacy | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ❌ |
| Smart Contract Privacy | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ | ❌ |
| Regulatory Compliance | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Selective Disclosure | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ | ✅ |
| Mainnet Settlement | ✅ | ✅ | ✅ | ❌ | ✅ | ✅ | ✅ |
| Primary Technology | FHE+GC | ZK+TEE | ZK | Privacy Groups | ZK | ZK | TEE |
| Trust Model | Org. Honesty | Crypto+HW | Cryptographic | Organizational | Cryptographic | Cryptographic | HW-Anchored |

## Solution Profiles

### Solution 1: COTI
- **Organization:** COTI Group
- **Technology:** FHE + Garbled Circuits
- **Trust Model:** Organizational Honesty (majority of co-processor operators)
- **Key Feature:** Data remains encrypted during computation; supports confidential smart contracts on Ethereum mainnet
- **Status:** Devnet with enterprise pilots

### Solution 2: Linea Enterprise (Consensys)
- **Organization:** Consensys
- **Technology:** ZK-Proofs + TEE hybrid
- **Trust Model:** Cryptographic + Hardware-Anchored
- **Key Feature:** Enterprise-grade privacy on Ethereum L2 with regulatory compliance built in
- **Status:** Enterprise pilot program active

### Solution 3: Nightfall (EY)
- **Organization:** Ernst & Young
- **Technology:** Zero-Knowledge Proofs (Optimistic ZK-Rollup)
- **Trust Model:** Cryptographic
- **Key Feature:** Privacy-first token transfers with regulatory compliance; EY's flagship blockchain privacy solution
- **Status:** Production-ready, deployed with enterprise clients

### Solution 4: Paladin (Kaleido, LFDT)
- **Organization:** Kaleido / LFDT Hyperledger
- **Technology:** Privacy Groups (notary-based)
- **Trust Model:** Organizational Honesty
- **Key Feature:** Private business logic execution with shared state commitments on public ledger
- **Status:** Production deployments

### Solution 5: Prividium (ZKsync / Matter Labs)
- **Organization:** ZKsync Foundation / Matter Labs
- **Technology:** Zero-Knowledge Proofs
- **Trust Model:** Cryptographic
- **Key Feature:** Enterprise privacy layer on ZKsync with confidential transactions
- **Status:** Development / pilot

### Solution 6: Agglayer CDK Enterprise (Polygon)
- **Organization:** Polygon
- **Technology:** Zero-Knowledge Proofs
- **Trust Model:** Cryptographic
- **Key Feature:** Customizable enterprise chains with privacy features via CDK
- **Status:** Active development

### Solution 7: Silent Data (Applied Blockchain)
- **Organization:** Applied Blockchain
- **Technology:** Trusted Execution Environments (TEE)
- **Trust Model:** Hardware-Anchored
- **Key Feature:** Off-chain data verification with on-chain attestation; bridges real-world data privately
- **Status:** Production

## Decision Framework

When evaluating privacy solutions, enterprises should consider:

1. **What needs to be private?** Transaction amounts, counterparty identities, business logic, or all three?
2. **What trust model is acceptable?** Pure cryptographic, hardware-dependent, or organizational?
3. **What is the regulatory environment?** GDPR, MiCA, or sector-specific requirements?
4. **What is the deployment timeline?** Production-ready vs. emerging technology?
5. **What is the integration complexity?** Mainnet settlement vs. separate chain?

No single solution addresses all enterprise privacy requirements. The optimal approach often involves combining solutions or selecting based on the specific use case.

## Future Outlook & Open Questions

- How will privacy solutions interact with each other across L1 and L2?
- What standards are needed for cross-solution interoperability?
- How will regulatory frameworks evolve to address on-chain privacy?
- What role will the EF Privacy Roadmap play in standardizing base-layer privacy?

## Contact

Enterprise Ethereum Alliance
entethalliance.org
press@entethalliance.org
