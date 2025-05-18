ZKStaking: A Zero-Knowledge Protocol for 
Cross-Chain Staking of ADA on the TAO 
Blockchain 
1. Abstract 
This whitepaper introduces ZKStaking, a protocol that enables ADA token holders on the 
Cardano blockchain to stake their assets in a verifiable way on the TAO (Bittensor) 
blockchain using zero-knowledge proofs (ZKPs). ZKStaking establishes a privacy
preserving, trust-minimized mechanism for proving staking behavior on one Layer 1 
(Cardano) to another Layer 1 (Bittensor), unlocking new avenues for cross-chain rewards and 
decentralized interoperability. 
2. Motivation 
Staking mechanisms in Proof-of-Stake (PoS) networks are generally siloed within their 
respective ecosystems. Cardano (ADA) offers a robust and secure staking protocol, yet its 
utility and influence are limited to the Cardano ecosystem. Conversely, Bittensor (TAO), a 
decentralized machine learning protocol, lacks integration with external blockchains and 
staking schemes. 
Zero-knowledge proofs provide a cryptographic means to prove knowledge or action without 
revealing sensitive data. By applying ZKPs to cross-chain staking, ZKStaking aims to: 
• Enable the use of staked ADA in decentralized applications on Bittensor. 
• Promote ecosystem interoperability. 
• Preserve privacy and minimize trust assumptions. 
3. Background 
3.1 Cardano Staking Model 
Cardano uses a Delegated Proof-of-Stake (DPoS) mechanism, allowing users to delegate 
ADA to staking pools via delegation certificates. Staking rewards are distributed 
proportionally based on the amount of ADA staked. 
Relevant Cardano components: 
• Stake credentials 
• Delegation certificates 
• Epoch-based reward cycles 
3.2 Bittensor (TAO) Architecture 
Bittensor is a decentralized network for machine learning models. It uses a custom consensus 
and staking system where TAO tokens are bonded by validators and miners within 
subnetworks. TAO lacks native smart contract support but supports extensible validator and 
miner behavior via hotkeys and off-chain interaction. 
3.3 Zero-Knowledge Proofs 
ZKPs allow one party (the prover) to convince another (the verifier) that a statement is true 
without revealing the underlying data. zkSNARKs and zkSTARKs are two prominent 
categories. 
Use cases: 
• Privacy-preserving transactions 
• Scalable off-chain computation 
• Proofs of behavior (e.g., staking) 
4. System Architecture 
4.1 Assumptions 
• The user holds ADA and stakes it through Cardano’s DPoS mechanism. 
• The Cardano blockchain can be queried for staking status. 
• A ZK proof can be generated to demonstrate ADA is staked to a known pool. 
• Bittensor validators can verify such a proof off-chain or via a custom mechanism. 
4.2 Workflow 
1. Stake ADA: User delegates ADA to a pool on Cardano. 
2. Generate ZK Proof: Off-chain prover constructs a ZK proof that the user is staking 
to a pool. 
3. Submit Proof: User submits the proof to a Bittensor validator or relayer. 
4. Validate Proof: Validator verifies the proof and acknowledges ADA stake. 
5. Distribute TAO Rewards: Bittensor allocates mining or staking rewards to the user 
accordingly. 
4.3 Architecture Diagram 
(To be included visually) 
• ADA Wallet → ZK Prover (Circom/Noir) → ZK Relayer → TAO Validator → 
Reward System 
5. Cryptographic Proof Design 
5.1 Data Proven 
• Stake credential is linked to the user. 
• Delegation certificate targets a known pool. 
• Minimum ADA stake is met. 
• Proof corresponds to current or recent Cardano epoch. 
5.2 ZK Circuit Components 
• Merkle proof of inclusion for delegation certificate. 
• Signature validation using Cardano’s address format. 
• Epoch verification within a defined range. 
• Optional: recursive SNARKs for scalability. 
6. Implementation Plan 
Phase 1: Specification & Research 
• Document Cardano staking certificate format. 
• Design ZK circuit with Circom or Noir. 
• Define protocol interfaces for TAO validators. 
Phase 2: Prototyping 
• Build ZK proof for ADA delegation. 
• Set up mock validator in Bittensor subnet. 
• Off-chain reward simulation based on verified proofs. 
Phase 3: Integration 
• Implement Mithril-based data availability layer. 
• Develop oracle or relayer interface between Cardano and Bittensor. 
• Evaluate staking reward formulas and slashing conditions. 
7. Challenges & Open Questions 
• On-chain Verifiability: Neither Cardano nor TAO supports generalized ZK proof 
verification natively. 
• Data Availability: Reliable access to Cardano chain state without running a full node. 
• Reward Synchronization: Aligning reward intervals and logic across chains. 
• Unstaking Events: Proving when a user unstakes or moves their funds. 
• Security: Preventing double claims or false proof submissions. 
8. Future Work 
• Full ZK light client for Cardano. 
• On-chain verifier module on Bittensor. 
• Expansion to other PoS chains like Ethereum 2.0 or Polkadot. 
• DAO-based governance to approve or reject proofs. 
• Decentralized relayers and proof markets. 
9. Conclusion 
ZKStaking demonstrates the feasibility and value of using zero-knowledge cryptography to 
bridge staking mechanisms across independent blockchains. By proving stake activity on 
Cardano in a trustless and privacy-preserving manner, users can unlock new functionality and 
rewards on the Bittensor network. While the protocol introduces challenges related to 
interoperability and proof verification, it also offers a powerful vision for the next generation 
of decentralized finance and cross-chain computation. 
10. References 
• Cardano Documentation: https://docs.cardano.org/ 
• Mithril: https://mithril.network/ 
• Bittensor: https://docs.bittensor.com/ 
• ZK Learning Resources: https://zk-learning.org/ 
• Circom: https://docs.circom.io/ 
• Noir: https://noir-lang.org/ 
