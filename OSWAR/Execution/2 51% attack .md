# 2. 51% attack

Category: Higher Privilige Attacks
Tags: Execution

### What is a "51% attack"?

A "51% attack" is an attack on a blockchain network. It occurs when an attacker gains control of more than 51% of the network's hash rate, which allows them to add new blocks to the chain faster than the rest of the network. This can result in the attacker being able to reverse transactions, double-spend coins, and potentially take control of the network. The attacker can effectively gain control over the network by creating a longer chain that invalidates previous transactions. A 51% attack also decreases the integrity of the blockchain and, therefore, can also be placed within “Impact”. 

Validators or miners in a blockchain network compete to add new blocks to the chain by solving complex cryptographic puzzles. The first validator to solve the puzzle and add the block to the chain is rewarded with cryptocurrency.

Validators or miners are responsible for verifying and adding new blocks. If an attacker gains control over most of the network's computational power, they can reverse previous transactions and double-spend coins. This can lead to a loss of trust in the network and significant financial damage to users.

### Example

Bitcoin underwent a 51% attack, which resulted in the creation of Bitcoin Cash. The attack occurred due to a disagreement within the early bitcoin community called the Block Wars. 

Mitigation:

There are several ways to reduce the risk of a 51% attack on a blockchain network:

1. Encourage decentralization: The community can make the network more decentralized by encouraging more participants to become validators or miners. This makes it more difficult for a single entity to gain control of the majority of the network's hash rate.
2. Implement consensus mechanisms: Consensus mechanisms like Proof-of-Stake (PoS) or Delegated Proof-of-Stake (DPoS) can help reduce the risk of a 51% attack. They require validators or miners to have a stake in the network.
3. Implement network monitoring: Network monitoring is essential to detect and respond to suspicious activity, including potential 51% attacks.

In summary, the best way to reduce the risk of a 51% attack is to encourage decentralization, implement consensus mechanisms, conduct regular audits and updates, implement network monitoring, promote diversity in mining hardware, and use checkpointing to protect past transactions. By taking a comprehensive approach to security, it is possible to reduce the risk of a 51% attack and preserve the integrity of the network.

Left out

---

A 51% attack could also fall under the "Command and Control" category, as the attacker would need to establish and maintain control over the compromised blockchain network to carry out the attack. However, the attack primarily falls under the "Resource Development" and "Execution" categories because it primarily involves acquiring the computing resources needed to control the majority of the network's mining power, and then using those resources to manipulate the blockchain's transaction history.

The attacker would first need to acquire the computing resources needed to control the network's mining power, which may involve purchasing or renting specialized hardware or using social engineering tactics to gain access to a large number of computers. Once the attacker has acquired the necessary computing resources, they would then use those resources to carry out the attack by mining blocks on the blockchain that contain fraudulent transactions, effectively manipulating the transaction history on the blockchain.

While the attacker may also need to establish some form of command and control infrastructure to maintain control over the compromised network, this aspect of the attack is secondary to the initial resource development and execution phases of the attack. Therefore, a 51% attack would primarily fall under the "Resource Development" and "Execution" categories.