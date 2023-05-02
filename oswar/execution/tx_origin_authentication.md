# 5.22 Tx.Origin Authentication

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “Tx. Origin Authentication”?

Solidity has a global variable, tx. origin, which traverses the entire call stack and returns the account address that originally sent the call (or transaction). Using this variable for authentication in smart contracts leaves the contract vulnerable to a phishing-like attack.

Contracts that authorize users to use the `tx.origin` variable are typically vulnerable to phishing attacks which can trick users into performing authenticated actions on the vulnerable contract.

Example:

Consider the simple contract,

```solidity
contract Phishable {
    address public owner;

    constructor (address _owner) {
        owner = _owner;
    }

    function () public payable {} // collect ether

    function withdrawAll(address _recipient) public {
        require(tx.origin == owner);
        _recipient.transfer(*this*.balance);
    }
}
```

This contract authorises the `withdrawAll()` function using `tx.origin`. This contract allows for an attacker to create an attacking contract of the form,

```solidity
import "Phishable.sol";

contract AttackContract {

    Phishable phishableContract;
    address attacker; // The attackers address to receive funds.

    constructor (Phishable _phishableContract, address _attackerAddress) {
        phishableContract = _phishableContract;
        attacker = _attackerAddress;
    }

    function () payable {
        phishableContract.withdrawAll(attacker);
    }
}
```

To utilize this contract, an attacker would deploy it and then convince the owner of the `Phishable` contract to send this contract some amount of ether. The attacker may disguise this contract as their own private address and social engineer the victim to send some form of transaction to the address. The victim, unless careful, may not notice that there is code at the attacker's address, or the attacker may pass it off as being a multi-signature wallet or some advanced storage wallet (remember, the source code of public contracts is not available by default).

In any case, if the victim sends a transaction (with enough gas) to the `AttackContract` address, it will invoke the fallback function, which in turn calls the `withdrawAll()` function of the `Phishable` contract, with the parameter `attacker`. This will result in the withdrawing all funds from the `Phishable` contract to the `attacker` address. This is because the address that first initialized the call was the victim (i.e. the `owner` of the `Phishable` contract). Therefore, `tx.origin` will be equal to `owner` and the `require` online [11] of the `Phishable` contract will pass.

Mitigation

`tx.origin` should not be used for authorization in smart contracts. This isn't to say that the `tx.origin` variable should never be used. It does have some legitimate use cases in smart contracts. For example, if one wanted to deny external contracts from calling the current contract, they could implement a `require` of the from `require(tx.origin == msg.sender)`. This prevents intermediate contracts from being used to call the current contract, limiting the contract to regular code-less addresses.