# 5.19 Block Timestamp Manipulation

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “Block timestamp manipulation”?

Block Timestamp Manipulation vulnerability is a type of vulnerability in smart contracts where an attacker can manipulate the timestamp of a block. The timestamp can be used in smart contracts to determine if a certain action can be executed, such as releasing funds after a certain period. If the timestamp can be manipulated, an attacker can trick the smart contract into executing an action prematurely or delaying it indefinitely.

Example: 

One real-world example of Block Timestamp Manipulation is the batchOverflow attack on the BEC token smart contract. In this attack, the attacker manipulated the block timestamp to cause an integer overflow when calculating the number of tokens to be transferred, transferring excessive tokens to the attacker's account.

Source: [https://ethereum.stackexchange.com/questions/46808/why-did-the-batchoverflow-hack-in-the-bec-contract-work](https://ethereum.stackexchange.com/questions/46808/why-did-the-batchoverflow-hack-in-the-bec-contract-work)

Mitigation: 

The mitigation for Block Timestamp Manipulation involves using a secure time source that attackers cannot manipulate. One solution is to use the block's median timestamp instead of its timestamp as a measure of time. Another solution is to use an external time source, such as an oracle, to provide the time for the smart contract. Additionally, developers should perform proper input validation and limit the number of funds transferred in a single transaction.