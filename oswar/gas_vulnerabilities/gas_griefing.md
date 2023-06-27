# Gas Griefing 

Category: Smart Contract Vulnerabilities
Tags: Gas Vulnerabilities

## What is GAS Griefing ?
Gas griefing attack happens when a user sends the amount of gas required to execute the target smart contract, but not its sub calls.Gas griefing attacks can occur on Contracts that take in data and utilize it in a sub-call to a different Contract. If this sub-call doesn't succeed, the entire transaction might either be reverted back or execution might continue. 

This can be particularly problematic for a relayer contract. In this case, the individual who carries out the transaction, known as the 'forwarder', can essentially block transactions by allocating just enough gas for the transaction to be executed, but not providing sufficient gas for the sub-call to be successful.

## An illustration of the Gas Griefing security vulnerability in technical terms
```js
pragma solidity ^0.5.0;

contract Relayer {

  function relay (Target target, bytes memory _data) public returns     (bool) 

  {

      (bool success,) = address(target).call(abi.encodeWithSignature("execute(bytes)", _data)); 
      // then send money to the user

      return success;

  }

}

contract Target {

  bool public result = false;

  function execute(bytes memory _data) public {

    uint j = 0;
    
    for(uint i;i<100;i++){

      j++;

    }

    result = true;

  }

  function setresult(bool v) public{

     result = v;

  }

} 
```
Assume the "Target" contract is the one with which the "Relayer" contract interacts.

The weakest contract is the relayer contract, and line 7 is where the weakness lies. Look closely at this line to notice the smart contract's attempt to invoke the Target smart contract's execute() function. The method continues to run without any issues because neither the amount of gas left in the tank nor the call's outcome is checked. The application functionality may be severely impacted by this behavior.

This only indicates that perhaps the smart contract "Target" did not correctly complete its execution (insufficient gas). Try raising the gas cap and running the smart contract method relay() once again to confirm this. You can now see that the value of the result variable has changed.
By adding gas checks before making the calls, you may prevent this behavior from causing vulnerability in the smart contract.

## Mitigations
Following are some options to Mitigate the Gas Griefing Issue.
- Only allow trusted users to relay transactions.
- Require that the forwarder provides enough gas.
- Perform gasEstimations before doing the transaction to the subcontract.

It is to be noted that Gas Griefing are difficult to mitigate since the gasEstimations can get wrong if transaction costs are high on the EVM.

## Reference
- https://swcregistry.io/docs/SWC-126
- https://www.getsecureworld.com/blog/smart-contract-gas-griefing-attack-the-hidden-danger/
- https://www.linkedin.com/pulse/gas-griefing-attack-olympix/?trk=pulse-article_more-articles_related-content-card
