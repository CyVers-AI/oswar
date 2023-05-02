# 5.15 Default Visibility

Category: Smart Contract Vulnerabilities
Tags: Execution

What is Default visibility?

Default visibilities vulnerability in Web3 refers to an exposure caused by the lack of access modifiers in Solidity contracts, which can lead to unexpected behavior and potentially malicious actions.

By default, Solidity contract functions have a public visibility level, meaning anyone can call them. This can lead to unintentional actions, such as transferring funds or modifying data, by anyone interacting with the contract.

For example, if a contract has a function that transfers funds to a specified address and it is set to public visibility, anyone can call this function and transfer funds to any address they choose. This can result in losing funds for the contract owner or users.

Example

The first Parity multi-sig hack

In the first Parity multi-sig hack, about $31M worth of Ether was stolen from primarily three wallets. A good recap of exactly how this was done is given by Haseeb Qureshi in [this post](https://medium.freecodecamp.org/a-hacker-stole-31m-of-ether-how-it-happened-and-what-it-means-for-ethereum-9e5dc29e33ce).

Mitigation

To mitigate this vulnerability, it is recommended to use access modifiers such as private, internal, and external to control the visibility and accessibility of functions and variables within a contract. Setting appropriate access levels can greatly reduce the potential for unexpected behavior and malicious actions.

```solidity
contract HashForEther {

    function withdrawWinnings() {
        // Winner if the last 8 hex characters of the address are 0.
        require(uint32(msg.sender) == 0);
        _sendWinnings();
     }

     function _sendWinnings() {
         msg.sender.transfer(this.balance);
     }
}
```