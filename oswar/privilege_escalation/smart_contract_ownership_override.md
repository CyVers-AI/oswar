# 1. Smart Contract Ownership Override:

Category: Higher Privilige Attacks
Tags: Privilege Escalation

What is the "smart contract ownership override"?

In this attack, an individual exploits a vulnerability in a smart contract to gain ownership. Once they have ownership, they can alter the contract to their preference, including providing greater access and control.

Smart contract override is a privilege escalation attack targeting smart contracts on a blockchain network. It is initiated when an attacker exploits a smart contract or network vulnerability that allows them to gain unauthorized access and control over the contract's operations. The attacker can then modify the contract's code, move funds, and execute malicious functions without the contract owner's awareness or permission. In the Web3 framework, smart contract override is classified as a privilege escalation attack. This is because the attacker gains elevated privileges over the smart contracts, enabling them to perform actions they would not typically have access to.

Here is an example:

Let's consider a smart contract that sets the price of a commodity such as real estate.

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.9;
contract RealEstatePrice {
 uint256 public apartmentprice;

 constructor(uint256 _price) {
   apartmentprice = _price; // default
 }

 function updateApartmentPrice(uint256 _price) external {
   apartmentprice = _price;
 }
}

```

*"The contract defined above is a simple real estate price. The constructor sets the default price for the apartment. The `updateApartmentPrice()` function updates the apartment price with the new one. The contract appears innocent; however, if you observe closely, the function `updateApartmentPrice()` is an external function and can be called by anyone (attacker) apart from the deployer or the owner to update the apartment pricing. This is a simple and classic example of an ownership attack where an attacker can call a function to update the value and easily exploit it."*

Mitigating

To prevent smart contract override attacks, there are several best practices that developers can follow:

- Use secure coding practices: Developers should follow secure codes when creating smart contracts, such as input validation, error handling, and parameter checks.
- Add a custom modifier that checks if you are the contract owner and only allows you to update the price in the function.
- Use secure contracts. Some contracts are well-tested, proven, efficient, and widely adopted; we can reuse the owner smart contract, preventing us from rewriting the modifier like above.
- Conduct thorough testing: Developers should conduct thorough testing of smart contracts to identify and address any potential vulnerabilities.
- Implement access controls: Smart contracts should be designed with proper access controls in place to limit the actions that users can perform.
- Use multi-signature wallets: Multi-signature wallets can be used to ensure that any changes to the smart contract require approval from multiple parties.
- Monitor smart contracts: Regularly monitoring smart contracts can help identify any unauthorized access or modifications to the contract's code.

---

Source: [https://blog.finxter.com/smart-contract-security-series-part-1-ownership-exploit/](https://blog.finxter.com/smart-contract-security-series-part-1-ownership-exploit/)