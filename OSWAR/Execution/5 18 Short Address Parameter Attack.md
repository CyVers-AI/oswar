# 5.18 Short Address/Parameter Attack

Category: Smart Contract Vulnerabilities
Tags: Execution

What is a Short Address/Parameter attack?
The Short Address/Parameter Attack vulnerability occurs when a contract or function doesn't validate the length of the input data. It allows an attacker to send a transaction with a shortened input, which can lead to unexpected behavior, including transferring funds to an unintended address or bypassing the intended logic of the contract. The attack is possible because Ethereum's virtual machine (EVM) pads the input data to a specific length, but it doesn't check if the input is that length.

Example:
In 2018, the smart contract of a blockchain-based game called Fomo3D was found to be vulnerable to a Short Address Attack. The contract was designed to allow players to buy keys and compete for a pot of Ether. However, the function that handled the purchase of keys didn't check the length of the input data, which allowed attackers to exploit the contract and drain the pot of Ether. By sending a transaction with a shortened input, the attacker could bypass the intended logic of the contract and transfer the Ether to their address.

Source: [https://www.apriorit.com/dev-blog/556-fomo3d-vulnerability](https://www.apriorit.com/dev-blog/556-fomo3d-vulnerability)

Mitigation:
Developers can mitigate the Short Address/Parameter Attack vulnerability by implementing input validation in their smart contracts. They should check the length of the input data and reject any transactions that don't meet the expected length. Additionally, contracts can use a checksum to verify the integrity of the input data. Using standardized interfaces, like ERC-20 and ERC-721, can also help mitigate the risk of this vulnerability, as these interfaces include standardized functions that validate input parameters. Finally, users can protect themselves by checking the address they are sending funds to, as some wallets automatically pad addresses to prevent this attack.