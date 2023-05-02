# 5.25 Self-destruct

Category: Smart Contract Vulnerabilities
Tags: Execution

What is the “self-destruct” function?

The "self-destruct" function in Solidity is a feature that allows a smart contract to be destroyed and its funds to be sent to a designated address. While this can be useful for cleaning up unused contracts and returning funds to investors, it can also be a potential vulnerability if not used properly.

Example:

One example of a vulnerability that can arise from the self-destruct function is when a contract's address is publicly available, and an attacker can call the self-destruct function on the contract, causing it to be destroyed. Its funds are to be sent to the attacker's address.

Another example is when a contract's self-destruct function is combined with a vulnerable function, such as a function that allows an attacker to set the self-destruct address. In this case, the attacker can set the self-destruct address to their own address and then call the vulnerable function, causing the contract to be destroyed and its funds to be sent to the attacker.

Mitigation:

To prevent self-destruct vulnerability, it is important to carefully consider the usage of the self-destruct function in a contract and to use it only when necessary. If the self-destruct function is used, it should only be called by an authorized user or function. The designated address should be carefully chosen to ensure funds are sent to the intended recipient. Additionally, contracts should be tested and audited regularly to ensure they remain secure as changes are made to the code.