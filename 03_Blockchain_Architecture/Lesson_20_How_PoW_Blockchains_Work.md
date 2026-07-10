### Lesson 20: How Proof of Work Blockchains Work

**1. Core Concept**

Proof of Work (PoW) relies on cryptographic hashing and brute-force computation to secure a decentralized ledger. Miners compete to solve complex mathematical puzzles by guessing a random number (a "nonce"). Once solved, the block is cryptographically linked to the previous one, ensuring that altering historical data would require re-mining the entire chain—an impossibly expensive task.

**2. Key Mechanisms**
* **Hashing (SHA256):** A cryptographic function that turns any input data into a fixed-length, deterministic string (a digital fingerprint). Even a single altered character changes the entire output unpredictably.
* **The Nonce & Mining:** To validate a block, miners must find a specific hash that starts with a required number of leading zeros (the difficulty). Since hashes are unpredictable, miners repeatedly guess a random number (the **nonce**) until they hit the correct output.
* **Block Linking (Immutability):** Every block contains the hash of the block before it (the `Prev` field). If an attacker changes data in Block #4, its hash changes, breaking the link to Block #5 and invalidating the entire subsequent chain.
* **The Longest Chain Rule:** When two miners solve a block simultaneously (a fork), the network temporarily splits. Nodes resolve this by always adopting the longest valid chain (the one with the most accumulated computational work) as the single source of truth.
* **Probabilistic Finality:** In PoW, transactions are never instantly permanent. They become increasingly secure with every new block mined on top of them (confirmations). Bitcoin typically considers a transaction fully secure after 6 confirmations.

**3. The "Why It Matters" (Security Perspective)**

The cryptographic link between blocks is the literal "chain" in blockchain, and it is the foundation of immutability. As a smart contract auditor, understanding this helps you grasp why reversing a transaction is practically impossible on massive networks like Bitcoin. If an attacker wants to fraudulently alter a past block, they must recalculate the nonce for that block, and then recalculate the nonces for every single block mined since, constantly outpacing the combined computational power of the rest of the network (a **51% Attack**). This mathematically guarantees that deep historical data cannot be manipulated.

**4. Terms to Remember**
* **Hash:** A unique, fixed-length digital fingerprint generated cryptographically from input data.
* **Nonce (Number Used Once):** The random number miners continuously guess to try and produce a valid block hash.
* **Genesis Block:** The very first block in a blockchain, which has no preceding block to link to.
* **Longest Chain Rule:** The consensus algorithm rule dictating that the chain with the most computational work is the valid state of the network.
* **Fork:** A temporary divergence in the blockchain when two valid blocks are mined at the exact same time.
