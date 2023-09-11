# 5.2 Reentrancy

Category: Smart Contract Vulnerabilities
Tags: Execution

What is a reentrancy attack?

A reentrancy attack is a vulnerability that can occur in a smart contract running on a blockchain platform. It happens when an attacker exploits a flaw in the smart contract's code to repeatedly call back into the contract before the previous invocation has been completed. This allows the attacker to drain the contract's funds or manipulate its state.

Example

In 2016, the DAO attack was an example of this hack. An attacker exploited a vulnerability in the DAO smart contract by calling a function that had a recursive call. This recursive call led to an overflow of the attacker's account balance, resulting in the attacker being able to withdraw Ether from the DAO's funds.

One example of the Unchecked Call Return Value hack is the infamous DAO attack on the Ethereum blockchain in 2016.

The DAO was a decentralized autonomous organization that aimed to operate as a venture capital fund for the blockchain industry. It raised over $150 million in Ether (ETH) through an initial coin offering (ICO). However, a vulnerability in the smart contract allowed an attacker to drain one-third of the funds, amounting to about $50 million in ETH.

The attacker used a combination of a reentrancy attack and the Unchecked Call Return Value vulnerability to exploit the smart contract. They used the DAO's function that allowed users to split their tokens and withdraw their share of the funds. However, the attacker created a recursive call loop by reentering the same function multiple times.

Additionally, the function call used to withdraw the funds did not check the return value of the recursive call. This allowed the attacker to repeatedly drain the funds until they could steal significant ETH from the DAO.

The DAO attack was a significant event in the history of blockchain technology, and it led to the Ethereum community hard-forking the blockchain to recover the stolen funds. The incident also highlighted the importance of conducting thorough security audits and testing smart contracts to identify and mitigate vulnerabilities like the Unchecked Call Return Value hack.

To prevent this type of attack, it is important to ensure that smart contracts validate the return value of every function call and that they implement proper exception-handling mechanisms to handle unexpected return values. Additionally, developers should follow best practices for smart contract development to minimize the risk of vulnerabilities and attacks on the blockchain.

Mitigation

To mitigate the risk of reentrancy attacks, developers must carefully design and test their smart contracts. Some specific measures that can be taken to prevent these attacks include:

- Implementing checks on the state of the contract before and after each call to prevent reentry
- Using mutex locks to prevent concurrent calls to the same function
- Limiting the amount of Ether that can be withdrawn from the contract at any one time
- Avoiding calling external contracts or functions within a smart contract, if possible
- Implementing fail-safes and emergency stop mechanisms to prevent significant losses in the event of an attack

By taking these steps and staying informed about the latest security best practices, developers can help protect their smart contracts and the users who rely on them.

Sources: 

1. [https://consensys.github.io/smart-contract-best-practices/known_attacks/#unchecked-call-return](https://consensys.github.io/smart-contract-best-practices/known_attacks/#unchecked-call-return)
2. [http://www.web3isgoinggreat.com/](http://www.web3isgoinggreat.com/)
3. [DeFi Protocol Attack Taxonomy (dPAT) by Rektify AI](https://github.com/RektifyAI/attack-playbook/blob/main/taxonomy/defi_taxonomy.md)

---

Left out:

- Single-Function Reentrancy
- Cross-Function Reentrancy
- Cross-Contract Reentrancy
- Cross-Chain Reentrancy
- Read-Only Reentrancy

Single-Function Reentrancy, Cross-Function Reentrancy, Cross-Contract Reentrancy, Cross-Chain Reentrancy and Read-Only Reentrancy are all different types of reentrancy attacks that can occur in a smart contract.

Single-Function Reentrancy occurs when an attacker repeatedly calls the same function within a smart contract before the previous invocation has finished executing, allowing them to manipulate the state of the contract or drain its funds.

Cross-Function Reentrancy involves an attacker exploiting vulnerabilities between different functions within the same smart contract, allowing them to repeatedly call back and forth between these functions to manipulate the contract's state or funds.

Cross-Contract Reentrancy occurs when an attacker exploits vulnerabilities between different smart contracts on the same blockchain platform, allowing them to repeatedly call back and forth between these contracts to manipulate their states or funds.

Cross-Chain Reentrancy occurs when a contract is on multiple chains and uses a bridge to connect these chains. An attacker can then exploit the logic of the contract in order to create multiple copies of an NFT and make it a fungible token by copying it on multiple chains.

Read-Only Reentrancy is a type of reentrancy attack that does not involve modifying the state or funds of a smart contract, but instead involves repeatedly reading sensitive data from the contract before the previous invocation has finished executing, allowing the attacker to gather information that could be used in other attacks.

In summary, all types of reentrancy attacks involve exploiting vulnerabilities in smart contract code to repeatedly call back into the contract before the previous invocation has finished executing. However, the specific type of attack and the scope of the vulnerabilities being exploited can vary depending on the context and design of the smart contract.

A reentrancy attack is a type of vulnerability that can occur in a smart contract running on a blockchain platform. It involves an attacker exploiting a flaw in the smart contract's code to repeatedly call back into the contract before the previous invocation has been completed, allowing them to drain the contract's funds or manipulate its state.

The attack works by taking advantage of the fact that smart contracts on blockchains operate in a deterministic and predictable manner. When a smart contract receives a transaction, it executes a set of pre-programmed instructions in a specific order. If the contract is designed poorly or contains a vulnerability, it may be possible for an attacker to exploit this order of execution to repeatedly call back into the contract, even while a previous call is still being processed.

In a reentrancy attack, the attacker first sends a transaction to the vulnerable contract, triggering the contract to execute a function. This function may include a call to an external contract or function. If the external contract contains a callback function that can be called by the original contract before the original call has finished executing, the attacker can exploit this vulnerability to repeatedly call back into the original contract, effectively "re-entering" the original function.

By doing this repeatedly, the attacker can drain the contract's funds or manipulate its state, potentially causing significant damage to the contract and its users.

Reentrancy attacks have been used to exploit vulnerabilities in various blockchain platforms, including Ethereum, and have led to significant losses for users and developers. As a result, it is important for developers to carefully design and test their smart contracts to avoid these types of vulnerabilities.
