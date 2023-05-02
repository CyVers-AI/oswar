# 5.20 Constructors with Care

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “Constructors with care”?
Constructors with Care is a vulnerability in Solidity smart contracts where the constructor function is not designed properly, leading to unexpected results and potential vulnerabilities. The constructor function is executed only once during the deployment of the contract, and it initializes the state variables of the contract. The issue arises when the constructor function does not take proper care of the variables and can lead to unintended behavior in the contract.

Constructors are special functions that often perform critical, privileged tasks when initializing contracts. Before solidity `v0.4.22`, constructors were defined as functions that had the same name as the contract that contained them. Thus, when a contract name gets changed in development, it becomes a normal, callable function if the constructor name isn't changed. As you can imagine, this has led to some interesting contract hacks.

For further reading, the reader should attempt the [Ethernaught Challenges](https://github.com/OpenZeppelin/ethernaut) (in particular, the Fallout level).

Vulnerability: If the contract name gets modified or there is a typo in the constructor's name such that it no longer matches the name of the contract, the constructor will behave like a normal function. This can lead to dire consequences, especially if the constructor performs privileged operations. Consider the following contract

```jsx
contract OwnerWallet {
    address public owner;

    //constructor
    function ownerWallet(address _owner) public {
        owner = _owner;
    }

    // fallback. Collect ether.
    function () payable {}

    function withdraw() public {
        require(msg.sender == owner);
        msg.sender.transfer(*this*.balance);
    }
}
```

This contract collects ether and only allows the owner to withdraw all the ether by calling the `withdraw()` function. The issue arises because the constructor is not exactly named after the contract. Specifically, `ownerWallet` is not the same as `OwnerWallet`. Thus, any user can call the `ownerWallet()` function, set themselves as the owner, and then take all the ether in the contract by calling `withdraw()`.

Example

Rubixi ([contract code](https://etherscan.io/address/0xe82719202e5965Cf5D9B6673B7503a3b92DE20be#code)) was another pyramid scheme exhibiting this vulnerability. It was originally called `DynamicPyramid`, but the contract name was changed before deployment to `Rubixi`. The constructor's name wasn't changed, allowing any user to become the `creator`. Some interesting discussions related to this bug can be found on this [Bitcoin Thread](https://bitcointalk.org/index.php?topic=1400536.60). Ultimately, it allowed users to fight for `creator` status to claim the fees from the pyramid scheme. More detail on this particular bug can be found [here](https://applicature.com/blog/history-of-ethereum-security-vulnerabilities-hacks-and-their-fixes).

Mitigation:

This issue has been primarily addressed in the Solidity compiler in version `0.4.22`. This version introduced a `constructor` keyword that specifies the constructor rather than requiring the function's name to match the contract name. As highlighted above, using this keyword to specify constructors is recommended to prevent naming issues.
To mitigate the Constructors with Care vulnerability, developers should properly initialize the variables in the constructor function and ensure it is designed to be executed only once. Additionally, contracts should be thoroughly tested and audited to ensure no unexpected behaviors. Best practices should be followed, and external libraries or contracts should be used when possible instead of creating custom code.

Source: [https://github.com/sigp/solidity-security-blog#constructors](https://github.com/sigp/solidity-security-blog#constructors)