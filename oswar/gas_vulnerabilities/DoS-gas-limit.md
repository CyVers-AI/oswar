# Denial of Service with Gas Limit

Category: Smart Contract Vulnerabilities
Tags: Gas Vulnerabilities

## What is DoS (Denial-of-Service)?
[Denial-of-Service (DoS) attack](https://github.com/RektifyAI/attack-playbook/blob/main/taxonomy/defi-taxonomy.md) 
is a malicious attempt to disrupt the normal traffic of a 
targeted server, service or network by overwhelming the network's server. DoS attacks are easy to trace.

## What is DoS with Gas Limit?

Each block has an upper bound on the amount of gas that can be spent, 
and thus the amount computation that can be done. This is the Block Gas Limit. 
If the gas spent exceeds this limit, the transaction will fail.

Denial-of-Service with Gas Limit is an attack that typically occurs when a developer does not
have a good understandning of Etheruem Virtual Machine (EVM). 

Not to harp on developers, but 
DoS with gas limit exploits can be prevented with the following methodology:


## An illustration of the Denial-of-Service with Gas Limit vulnerability:
```js
pragma solidity 0.8.19;

contract InsecureNaiveBank {
    uint256 public constant INTEREST_RATE = 5;  // 5% interest

    mapping (address => uint256) private userBalances;
    address[] private userAddresses;

    address public immutable owner;

    constructor() {
        owner = msg.sender;
    }

    modifier onlyOwner() {
        require(owner == msg.sender, "You are not the owner");
        _;
    }

    function depositBankFunds() external payable onlyOwner {
        require(msg.value > 0, "Require some funds");
    }

    // There is a double spending issue on the depositFor() function, 
    // but it is not the scope of this example though
    function depositFor(address _user) external payable {
        require(_user != address(0), "Do not support a zero address");
        require(msg.value > 0, "Require some funds");

        // Register new user
        if (userBalances[_user] == 0) {
            userAddresses.push(_user);
        }

        userBalances[_user] += msg.value;
    }

    function withdraw(uint256 _withdrawAmount) external {
        require(userBalances[msg.sender] >= _withdrawAmount, "Insufficient balance");
        userBalances[msg.sender] -= _withdrawAmount;

        (bool success, ) = msg.sender.call{value: _withdrawAmount}("");
        require(success, "Failed to send Ether");
    }

    function applyInterest() external onlyOwner returns (uint256 minBankBalanceRequired_) {
        for (uint256 i = 0; i < userAddresses.length; i++) {
            address user = userAddresses[i];
            uint256 balance = userBalances[user];

            // Update user's compound interest
            userBalances[user] = balance * (100 + INTEREST_RATE) / 100;

            // Calculate the minimum bank balance required to pay for each user
            minBankBalanceRequired_ += userBalances[user];
        }
    }

    function getBankBalance() external view returns (uint256) {
        return address(this).balance;
    }

    function getUserBalance(address _user) external view returns (uint256) {
        return userBalances[_user];
    }

    function getUserLength() external view returns (uint256) {
        return userAddresses.length;
    }
}
```

The ```applyInterest``` function iterates over all despositor accounts that interact with the ```InsecureNaiveBank```
contract. If there are too many depositor accounts, the iteration will consume more gas than the block
gas limit. When this DoS occurs, the transaction reverts when the banker (receiver contract) calculates
depositors' compound interests. This makes the ```InsecureNaiveBank``` contract inoperable, rendering it 
useless as a banking mechanism.


## Mitigations
Following are some options to mitigate the Denial of Service with Gas Limit.
- Redesign how to process depositors' interests in the context of DoS threat.
- Enable banker (receiver contract) to process multiple transactions.
- Perform gasEstimations before doing the transaction to the subcontract.

Great news! DoS in Gas Limit can be mitigated and remediated! Don't fret.

## Reference
- [Denial of Service With Gas Limit](https://github.com/serial-coder/solidity-security-by-example/tree/main/10_denial_of_service_with_gas_limit)
- [Consensys Ethereum Smart Contract Best Practices: Denial of Service](https://consensys.github.io/smart-contract-best-practices/attacks/denial-of-service/)
- [Medium Article: Solidity Security By Example #10: Denial of Service With Gas Limit](https://medium.com/valixconsulting/solidity-security-by-example-10-denial-of-service-with-gas-limit-346e87e2ef78)
- [SWC Registry: SWC-128](https://swcregistry.io/docs/SWC-128)
