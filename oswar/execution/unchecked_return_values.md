# 5.9 Unchecked Return Values

Category: Smart Contract Vulnerabilities
Tags: Execution

What is Unchecked Return Values?

Unchecked return values are a vulnerability category within the "Exploitation" stage of the attack lifecycle. This vulnerability occurs when a smart contract function call returns a value, but the calling contract fails to verify or use the returned value, leaving it unchecked.

There are several ways of performing external calls in Solidity. Sending ether to external accounts is commonly performed via the `transfer` method. However, the `send` function can also be used, and for more versatile external calls, the `CALL` opcode can be directly employed in Solidity.

You can send Ether to other contracts by

- `transfer` (2300 gas, throws an error)
- `send` (2300 gas, returns bool)
- `call` (forward all gas or set gas, returns bool)

Here we can see that when we use to send or call to send ether or perform any transactions, it returns a boolean value i.e. true or false.

The `call` and `send` functions to return a Boolean indicating whether the call succeeded or failed. As a result, if the call return value is not checked, execution will resume even if the called contract throws an exception. If the call fails accidentally or an attacker forces the call to fail, this may cause unexpected behavior in the subsequent program logic.

![https://miro.medium.com/v2/resize:fit:1400/1*x2t4bTbgy1TqUPwymfz62A.png](https://miro.medium.com/v2/resize:fit:1400/1*x2t4bTbgy1TqUPwymfz62A.png)

In the above code, you can see that there is a Transfer function that uses a call method to transfer the amount. In the first case, it doesn’t check for the return value, where there is no error handling if the transfer fails.

In the second one, there is a check for the call's return value. If the call fails it will revert with a “transfer failed” message.

Real-World Example:

When sending ETH from one contract to another, like from the King of the Ether contract to an Ethereum Mist "contract-based wallet" contract, it's possible for the transfer to fail if implemented in the "obvious" way in the Solidity contract language due to insufficient gas.

This resulted in failed transfers from the Kings of Ether contract to users. Without any checks for the call return value, a failed transaction was recorded as a completed transaction in the contract.

Source 1: **[KotET - Post-Mortem Investigation During the 'Turbulent Age' (06 Feb 2016 to 08 Feb 2016) of the King of the Ether Throne, a serious issue caused some…**
www.kingoftheether.com](https://www.kingoftheether.com/postmortem.html)

**Real World example is**:

- [King of the Ether](https://www.kingoftheether.com/postmortem.html)
- [Etherpot](http://aakilfernandes.github.io/blockhashes-are-only-good-for-256-blocks)

Source 2: [https://sm4rty.medium.com/unchecked-call-return-value-solidity-security-1-fe794a7cdb6f](https://sm4rty.medium.com/unchecked-call-return-value-solidity-security-1-fe794a7cdb6f)

Mitigation: 

If send or call is used, Always make sure to handle the possibility that the call will fail, by checking the return value.

To mitigate this vulnerability, developers should ensure that their smart contracts properly handle and verify all return values. This includes checking for errors and verifying that the expected value was returned before proceeding with further actions. Additionally, developers should use tools such as static analysis and code reviews to identify and address potential unchecked return value vulnerabilities before deploying smart contracts.