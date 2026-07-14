### Lesson 26: A Deep Dive into Ethereum Gas Fees & EIP-1559

**1. Core Concept**
Gas is the computational fuel of the Ethereum Virtual Machine (EVM). Every operation—from sending ETH to executing complex smart contracts—requires a fee. This fee serves two absolute purposes: it compensates validators for their hardware/energy costs, and it creates a financial barrier to prevent attackers from spamming and halting the network.

<Image src="image_agent_tag_1517540231468517433" alt="Diagram showing Pre EIP-1559 all fees going to miners, and Post EIP-1559 showing the base fee being burned while the tip goes to validators" caption="EIP-1559 Fee Mechanics" />

**2. Key Mechanisms**
* **Gas vs. Gas Price:** "Gas" is the fixed computational weight of an action (e.g., an ETH transfer always costs 21,000 gas). "Gas Price" is how much you are willing to pay per unit of that weight, typically measured in **Gwei**.
* **Denominations:**
  * **Wei:** The absolute smallest unit of ETH ($1 \text{ ETH} = 10^{18} \text{ Wei}$).
  * **Gwei:** Giga-Wei, or one billion Wei ($1 \text{ ETH} = 10^{9} \text{ Gwei}$). Gas prices are almost exclusively quoted in Gwei.
* **Type 0 (Legacy) Transactions:** The old "first-price auction" model. Users blindly guessed a single `gasPrice`. If you guessed too low during network congestion, your transaction would remain stuck in the mempool for days.
* **Type 2 (EIP-1559) Transactions:** The modern standard that splits the fee into two parts:
  * **Base Fee:** An algorithmically determined, mandatory ticket price based on how full the previous block was. Crucially, this fee is **burned** (destroyed), creating deflationary pressure on the ETH supply.
  * **Priority Fee (Tip):** An optional incentive paid directly to the validator to prioritize your transaction over others.

**3. The "Why It Matters" (Security Perspective)**
As a developer or auditor, understanding EIP-1559 is critical for user experience and contract architecture. If your Decentralized Application (dApp) hardcodes legacy Type 0 gas calculations, your users will chronically overpay for transactions or get their transactions stuck when network congestion spikes. Furthermore, understanding the algorithmic Base Fee is vital for MEV (Maximal Extractable Value) analysis. When a highly anticipated NFT mint or token launch occurs, the demand for block space skyrockets, mathematically driving the Base Fee up exponentially block-by-block. If a smart contract is incredibly gas-inefficient, this spike can make it economically impossible for regular users to interact with it.

**4. Terms to Remember**
* **Gas Limit:** The absolute maximum amount of computational units a user authorizes a transaction to consume before it aborts.
* **Base Fee:** The mandatory, algorithmically adjusted minimum gas price required for a transaction to be included in a block. It is always burned.
* **Priority Fee:** The "tip" paid directly to the validator to incentivize faster block inclusion.
* **EIP-1559:** The monumental network upgrade (implemented during the London Hard Fork) that introduced the Base Fee and burning mechanics to make transaction costs predictable.
