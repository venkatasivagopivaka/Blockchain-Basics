### Lesson 15: Sending Your First Transaction on a Public Testnet

**1. Core Concept**

Interacting with a public blockchain requires navigating a live, decentralized environment. This process involves sourcing test currency from a public faucet, executing a transaction via a wallet, and independently verifying the network's immutable ledger using a block explorer. This workflow represents the fundamental lifecycle of all on-chain activity.

**2. Key Mechanisms**
* **Public Faucets:** Developer tools (like the Google Cloud Web3 Faucet) that dispense free testnet ETH. Because public testnets require real computation, transactions still cost "gas," making this test currency mandatory for development.
* **Transaction Execution:** Sending funds requires specifying a recipient address and a transaction amount, while ensuring enough test ETH remains to cover the network's gas fee.
* **Block Explorers (The Immutable Ledger):** Web applications (like Etherscan or Blockscout) that provide a readable interface for the blockchain. They allow anyone to transparently track balances, view transaction histories, and verify activity.
* **Transaction Hash (TxHash):** A unique cryptographic identifier generated for every single transaction. It acts as a digital receipt, allowing you to track the status, timestamp, and gas cost of a transfer on the block explorer.

**3. The "Why It Matters" (Security Perspective)**

In Web3, your wallet interface (like MetaMask) can lie to you, but the blockchain cannot. A malicious website or a compromised front-end can trick a wallet into displaying a fake token balance or a misleading transaction request. As an auditor, you must treat the block explorer (like Etherscan) as the absolute source of truth. When a protocol is hacked, the forensic investigation happens entirely on the block explorer—analyzing raw TxHashes to trace exactly where the funds moved, how much gas was spent, and which smart contract functions the attacker exploited.

**4. Terms to Remember**
* **Gas Fee:** The computational cost required to process and validate a transaction on the Ethereum network.
* **Block Explorer:** A search engine for the blockchain (e.g., Etherscan) used to view transparent ledger data.
* **TxHash (Transaction Hash):** The unique, permanent ID assigned to a specific transaction on the blockchain.
* **Sepolia:** The primary public testnet for Ethereum application development.
