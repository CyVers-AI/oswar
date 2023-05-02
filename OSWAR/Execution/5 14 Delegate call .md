# 5.14 Delegate call

Category: Smart Contract Vulnerabilities
Tags: Execution

What is a “Delegate call” vulnerability?

The delegate call vulnerability is a vulnerability in smart contracts on the Ethereum blockchain that allows attackers to call a function in another contract with all of the calling contract's context, including the contract's storage, balance, and code. This vulnerability can allow attackers to take control of a contract or steal funds from it by exploiting the trust relationship between contracts. 

The vulnerability arises because of the delegatecall() function, which can be used to call a function in another contract and is commonly used to implement libraries in Solidity. However, if the input data is not properly validated, an attacker can execute malicious code and take control of the calling contract.

Examples: 

Parity multi-sig (wallet hack)

The second Parity multi-sig wallet hack is an example of how the context of well-written library code can be exploited if run in its non-intended context. Several good explanations of this hack exist, such as this overview: [Parity MultiSig Hacked. Again](https://medium.com/chain-cloud-company-blog/parity-multisig-hack-again-b46771eaa838) by Anthony Akentiev, this [stack exchange question](https://ethereum.stackexchange.com/questions/30128/explanation-of-parity-library-suicide/30130) and [An In-Depth Look at the Parity Multisig Bug](http://hackingdistributed.com/2017/07/22/deep-dive-parity-bug/).

Mitigation

*“Solidity provides the `library` keyword for implementing library contracts (see the [Solidity Docs](http://solidity.readthedocs.io/en/latest/contracts.html?highlight=library#libraries) for further details). This ensures the library contract is stateless and non-self-destructable. Forcing libraries to be stateless mitigates the complexities of storage context demonstrated in this section. Stateless libraries also prevent attacks whereby attackers modify the state of the library directly to affect the contracts that depend on the library's code. As a general rule of thumb, when using `DELEGATECALL` pay careful attention to the possible calling context of both the library contract and the calling contract, and whenever possible, build state-less libraries.”*

- [https://blog.sigmaprime.io/solidity-security.html#dc-example](https://blog.sigmaprime.io/solidity-security.html#dc-example)