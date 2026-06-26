### Lesson 02: History and Evolution

**1. Core Concept**
The blockchain evolution began as a solution to the "Double-Spend Problem"—creating a digital currency without a central intermediary. This evolved from Bitcoin (a decentralized calculator/store of value) to Ethereum (a decentralized computer/execution layer for agreements).

**2. Key Mechanisms**
* **Double-Spend Resolution:** By distributing the ledger to everyone, the network prevents the same unit of currency from being spent twice, replacing the need for a bank to validate transactions.
* **Byzantine Generals Problem:** A classic distributed computing challenge where a network must reach consensus (agreement) even if some participants are malicious. Bitcoin’s blockchain provides the solution to this consensus problem.
* **Smart Contracts:** Programmable "unbreakable agreements" where the logic is written in code and enforced by the network, removing the need for traditional intermediaries (lawyers, title agents, etc.).
* **Credible Neutrality:** The system is impartial, permissionless, and censorship-resistant. It processes transactions based on code, not the identity of the user.

**3. The "Why It Matters" (Security Perspective)**
* **Surface Area:** Bitcoin is "Turing incomplete" by design; its limited features reduce the potential attack surface, making it extremely secure as a store of value. 
* **The "Code is Law" Risk:** Ethereum is "Turing complete," meaning it can execute complex logic. This makes it infinitely more useful but also introduces risk. In smart contract auditing, "Code is Law" is a double-edged sword: if the logic in the code is flawed (e.g., a reentrancy bug), the "Law" of the contract will execute that flaw, and there is no human intermediary to reverse it. As an auditor, your job is to ensure that the "Law" behaves exactly as intended.

**4. Terms to Remember**
* **Double-Spend Problem:** The risk that a digital asset can be copied and spent multiple times.
* **Byzantine Generals Problem:** The dilemma of how a distributed network achieves consensus when individual components may be malicious.
* **Turing Complete:** A system capable of solving any computational problem (Ethereum can run any program; Bitcoin is limited).
* **Smart Contract:** Self-executing code that automatically enforces the terms of an agreement on the blockchain.
