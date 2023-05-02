# 5.6 Integer overflow/Underflow

Category: Smart Contract Vulnerabilities
Tags: Execution

What is Integer underflow/overflow?

Underflow/overflow issues can occur in smart contracts when performing mathematical operations on integers without proper bounds checking. For example, if a smart contract subtracts a larger number from a smaller one, it can result in an underflow and unexpected results. Similarly, if a smart contract adds a number to a value already at the maximum limit of the variable, it can result in an overflow.

Attackers can exploit these types of vulnerabilities to manipulate the behavior of the smart contract and steal funds. Therefore, it is essential for smart contract developers to implement proper bounds checking and testing to prevent these types of issues.

These are issues that usually get patched during audits. 

In computer programming, an integer overflow/underflow occurs when an arithmetic operation on an integer exceeds the maximum or minimum value that the data type can represent. An overflow/underflow can cause unexpected behavior in a program, including incorrect results or program crashes. In the context of Web3, integer overflow/underflow can occur in smart contracts when a mathematical operation on a variable exceeds the maximum or minimum value that can be represented by its data type, potentially leading to incorrect results or even financial losses.

Example

For example, in a smart contract that manages a token, an integer overflow can occur when a user attempts to transfer more tokens than they have, causing the contract to interpret the integer value as a negative number and resulting in an unintended transfer of tokens.

****TimeLock.sol****

```solidity
contract TimeLock {
    
    mapping(address => uint) public balances;
    mapping(address => uint) public lockTime;
    
    function deposit() public payable {
        balances[msg.sender] += msg.value;
        lockTime[msg.sender] = now + 1 weeks;
    }
    
    function increaseLockTime(uint _secondsToIncrease) public {
        lockTime[msg.sender] += _secondsToIncrease;
    }
    
    function withdraw() public {
        require(balances[msg.sender] > 0);
        require(now > lockTime[msg.sender]);
        msg.sender.transfer(balances[msg.sender]);
        balances[msg.sender] = 0;
    }
}
view rawTimeLock.sol hosted with ❤ by GitHub
```

“*This contract is designed to act like a time vault, where users can deposit ether into the contract and it will be locked there for at least a week. The user may extend the time longer than 1 week if they choose, but once deposited, the user can be sure their ether is locked in safely for at least a week. Or can they?…*

*In the event a user is forced to hand over their private key (think hostage situation) a contract such as this may be handy to ensure ether is unobtainable in short periods of time. If a user had locked in `100 ether` in this contract and handed their keys over to an attacker, an attacker could use an overflow to receive the ether, regardless of the `lockTime`.*

*The attacker could determine the current `lockTime` for the address they now hold the key for (its a public variable). Let's call this `userLockTime`. They could then call the `increaseLockTime` function and pass as an argument the number `2^256 - userLockTime`. This number would be added to the current `userLockTime` and cause an overflow, resetting `lockTime[msg.sender]` to `0`. The attacker could then call the `withdraw` function to obtain their reward.”*

Mitigation

*The (currently) conventional technique to guard against under/overflow vulnerabilities is to use or build mathematical libraries which replace the standard math operators; addition, subtraction, and multiplication (division is excluded as it doesn’t cause over/underflows, and the EVM throws on division by 0).*

[*OppenZepplin](https://github.com/OpenZeppelin/zeppelin-solidity) has done a great job building and auditing secure libraries, which the Ethereum community can leverage. In particular, their [Safe Math Library](https://github.com/OpenZeppelin/zeppelin-solidity/blob/master/contracts/math/SafeMath.sol) is a reference or library to use to avoid under/overflow vulnerabilities.*

*To demonstrate how these libraries are used in Solidity, let us correct the `TimeLock` contract using Open Zepplin's `SafeMath`library. The overflow-free contract would become:*

Source: [https://medium.com/hackernoon/hackpedia-16-solidity-hacks-vulnerabilities-their-fixes-and-real-world-examples-f3210eba5148](https://medium.com/hackernoon/hackpedia-16-solidity-hacks-vulnerabilities-their-fixes-and-real-world-examples-f3210eba5148)

To mitigate the risk of integer overflow/underflow vulnerabilities in smart contracts, developers can follow best practices such as:

- Careful selection of variable data types: Developers should choose variable data types representing the maximum and minimum values required by the smart contract's operations.
- Use of SafeMath libraries: SafeMath is a library that provides safe arithmetic operations for uint variables in Solidity, the programming language used to write Ethereum smart contracts. This library ensures that arithmetic operations do not result in integer overflow or underflow.
- Code review / Audits: Smart contracts should be thoroughly audited by experienced developers and security experts to identify and mitigate potential vulnerabilities, including integer overflow/underflow issues.
- Testing: Smart contracts should be tested extensively to ensure they function as intended and do not contain any vulnerabilities, including integer overflow/underflow vulnerabilities.