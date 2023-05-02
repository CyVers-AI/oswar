# 5.21 Uninitialized storage pointers

Category: Smart Contract Vulnerabilities
Tags: Execution

What are “Uninitialized storage pointers”?

Uninitialized storage pointers vulnerability occurs when a smart contract uses uninitialized storage pointers that can be modified by a potential attacker, allowing them to write malicious code or steal funds. Storage pointers are variables used with smart contracts to store information on the blockchain. Uninitialized storage pointers occur when a developer fails to assign an initial value to a storage pointer.

The EVM stores data either as `storage` or as `memory`. Understanding exactly how this is done and the default types for local variables of functions is highly recommended when developing contracts. This is because it can produce vulnerable contracts by inappropriately initializing variables.

To read more about `storage` and `memory` in the EVM, see the [Solidity Docs: Data Location](http://solidity.readthedocs.io/en/latest/types.html#data-location), [Solidity Docs: Layout of State Variables in Storage](http://solidity.readthedocs.io/en/latest/miscellaneous.html#layout-of-state-variables-in-storage), [Solidity Docs: Layout in Memory](http://solidity.readthedocs.io/en/latest/miscellaneous.html#layout-in-memory).

*This section is based off the excellent [post by Stefan Beyer](https://medium.com/cryptronics/storage-allocation-exploits-in-ethereum-smart-contracts-16c2aa312743). Further reading on this topic can be found in Sefan's inspiration, which is this R[eddit thread](https://www.reddit.com/r/ethdev/comments/7wp363/how_does_this_honeypot_work_it_seems_like_a/).*

Local variables within functions default to `storage` or `memory` depending on their type. Uninitialized local `storage` variables can point to other unexpected storage variables in the contract, leading to intentional (i.e., the developer intentionally puts them there to attack later) or unintentional vulnerabilities.

Example:

A honey pot named OpenAddressLottery ([contract code](https://etherscan.io/address/0x741f1923974464efd0aa70e77800ba5d9ed18902#code)) was deployed that used this uninitialized storage variable query to collect ether from some would-be hackers. The contract is in-depth, so I will leave the discussion to this R[eddit thread](https://www.reddit.com/r/ethdev/comments/7wp363/how_does_this_honeypot_work_it_seems_like_a/), where the attack is clearly explained.

Another honey pot, CryptoRoulette ([contract code](https://etherscan.io/address/0x8685631276cfcf17a973d92f6dc11645e5158c0c#code)), also uses this trick to collect some ether. If you need help figuring out how the attack works, see [An analysis of a couple of Ethereum honeypot contracts](https://medium.com/@jsanjuas/an-analysis-of-a-couple-ethereum-honeypot-contracts-5c07c95b0a8d) for an overview of this contract and others.

Mitigation:

The Solidity compiler raises uninitialized storage variables as warnings. Thus developers should pay careful attention to these warnings when building smart contracts. The current version of mist (0.10) doesn't allow these contracts to be compiled. It is good practice to explicitly use the `memory` or `storage` keywords when dealing with complex types to ensure they behave as expected as of Solidity version `0.5.0`use of `memory` and `storage`are mandatory.

To mitigate this vulnerability, developers should ensure that all storage pointers are initialized with a default value, such as zero or null, before being used in the smart contract. Developers should also perform thorough testing and auditing of their smart contracts to identify and address potential vulnerabilities before deploying them on the blockchain. Additionally, developers should follow best practices for secure codings, such as using secure development frameworks and the principle of least privilege.

Source:

[https://github.com/sigp/solidity-security-blog#storage](https://github.com/sigp/solidity-security-blog#storage)