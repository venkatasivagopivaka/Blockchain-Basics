### Lesson 22: How Proof of Stake (PoS) Blockchains Work

**1. Core Concept**

Proof of Stake (PoS) replaces the massive energy expenditure of Proof of Work (PoW) with a system of financial collateral. Instead of "miners" competing with hardware, the network is secured by "validators" who lock up (stake) native cryptocurrency. The protocol’s security is derived from economic game theory: honest behavior is rewarded with issuance/fees, while malicious behavior is punished via **Slashing**—the permanent destruction of staked capital.

**2. Key Mechanisms**
* **The Validator:** A network participant who stakes collateral (e.g., 32 ETH) to gain the right to propose and attest to blocks.
* **Proposing and Attesting:** In each "slot" (12 seconds on Ethereum), one validator is pseudo-randomly chosen to propose a block. A committee of other validators then "attests" (votes) on the validity of that block.
* **Finality (Justified $\rightarrow$ Finalized):** PoS uses a multi-stage consensus process. A block becomes "Justified" when 2/3 of total stake approves it. Once the next block is also justified, the previous one reaches "Finality," making it mathematically irreversible.
* **Slashing:** The primary security enforcement mechanism. Validators who attempt to cheat (e.g., proposing contradictory blocks) have their stake destroyed (burned). This makes attacking the network financially ruinous.

**3. The "Why It Matters" (Security Perspective)**

In PoW, if you have 51% of the hash power, you can reorganize the chain. In PoS, the attack vector is different: **Stake Corruption**. If an attacker gathers 67% of the total staked ETH, they can potentially finalize fraudulent blocks. However, because the attacker must hold the *majority of all staked assets*, they are effectively attacking their own net worth. Any attempt to break the chain would tank the value of the very asset they are holding, creating a "self-defeating" security model. Auditors must understand that in PoS, the consensus rules are just as much about **economics** as they are about **cryptography**.

**4. Terms to Remember**
* **Validator:** A participant who locks up collateral to secure the network, propose blocks, and vote on validity.
* **Staking:** The act of locking up native cryptocurrency as collateral to participate in network validation.
* **Slashing:** The destructive penalty for malicious validator behavior where a portion of the staked collateral is burned.
* **Attestation:** A cryptographic vote cast by a validator to confirm that a proposed block is valid.
* **Finality:** The guarantee that a block's data is permanently immutable and cannot be rolled back.
