# 5.17 External contract referencing

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “External contract referencing”?

External Contract Referencing (ECR) is a vulnerability that arises when a smart contract relies on an external contract whose address can be changed by an attacker. This can occur when a smart contract references another contract to perform a specific function. Still, the address of the external contract is not fixed or hard coded in the smart contract. An attacker can exploit this vulnerability by changing the address of the external contract, causing the smart contract to interact with a malicious contract and potentially leading to unauthorized access or data theft.

Example:

An example of ECR vulnerability is the King of the Ether smart contract game developed in 2016. The game was designed to be played by depositing Ether into a smart contract, with the winner being the player who deposits the most Ether within a specific time frame. However, the smart contract relied on an external contract for some of its functionality, and the address of this external contract was not hard coded. This allowed an attacker to exploit the vulnerability by deploying a malicious contract with the same name as the external contract and changing its address. The attacker then called the functions in the malicious contract instead of the intended external contract, allowing them to steal the deposited Ether and win the game.

Source: [https://hackernoon.com/smart-contract-attacks-part-2-ponzi-games-gone-wrong-d5a8b1a98dd8](https://hackernoon.com/smart-contract-attacks-part-2-ponzi-games-gone-wrong-d5a8b1a98dd8)

Mitigation:

To mitigate the ECR vulnerability, developers should ensure that the addresses of all external contracts that a smart contract relies on are hardcoded within the smart contract. This makes it more difficult for an attacker to change the address of the external contract and exploit the vulnerability. Additionally, developers should perform extensive testing and auditing to identify and address potential vulnerabilities in their smart contracts.