### Lesson 29: Temporary Smart Wallets (EIP-7702)

**1. Core Concept**

While Smart Wallets (Account Abstraction) offer incredible features, migrating to them forces users to abandon their old wallet addresses and manually transfer all their assets. **EIP-7702** solves this massive friction by allowing a standard Externally Owned Account (EOA) to temporarily "borrow" the code of a smart contract for a single transaction. This grants the EOA temporary superpowers (like transaction batching) and immediately reverts it back to a normal EOA once the transaction concludes.

**2. Key Mechanisms**
* **The Migration Problem:** Moving from an EOA to a Smart Wallet traditionally requires generating a completely new 0x address and paying high gas fees to move NFTs, tokens, and ETH to the new account.
* **Delegation:** EIP-7702 allows an EOA to sign a transaction that delegates its execution to a specific smart contract. For that single transaction, the EOA behaves exactly as if it were that smart contract.
* **Type 4 Transactions:** Ethereum has evolved its transaction architecture over time (Type 0 = Legacy, Type 2 = EIP-1559, Type 3 = Blobs). EIP-7702 introduces **Type 4 Transactions**, which carry the specific authorization data needed for this temporary smart contract delegation.
* **Practical Use Case (Batching):** Instead of signing three separate transactions to Approve, Swap, and Transfer tokens, a Type 4 transaction delegates these actions to a "batching" contract, executing all three steps simultaneously with a single user signature.

**3. The "Why It Matters" (Security Perspective)**

From an auditing perspective, EIP-7702 introduces a terrifying new attack vector: **Malicious Delegation**. If a user is tricked into signing a Type 4 transaction that delegates their EOA to a malicious smart contract, that contract effectively gains total control over the EOA's state for the duration of the transaction, allowing it to instantly drain all assets. To prevent this, major wallet providers like MetaMask do not allow users to delegate to arbitrary contracts. Instead, they strictly hardcode trusted, heavily audited smart contracts within the wallet extension to safely handle the delegation routing.

**4. Terms to Remember**
* **EIP-7702:** The Ethereum upgrade that allows standard EOAs to temporarily function as smart contracts.
* **Delegation:** Granting a smart contract permission to execute logic on behalf of your EOA.
* **Type 4 Transaction:** The specific transaction structure introduced by EIP-7702 to handle temporary delegation.
* **Transaction Batching:** The ability to bundle multiple on-chain actions (Approve, Swap, Send) into a single atomic transaction requiring only one signature.
