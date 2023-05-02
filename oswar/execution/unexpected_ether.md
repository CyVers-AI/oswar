# 5.3 Unexpected Ether

Category: Smart Contract Vulnerabilities
Tags: Execution

What is "Unexpected Ether"?

The vulnerability known as "Unexpected Ether" is a reentrancy attack that can occur in smart contracts. It happens when a smart contract receives Ether as payment and calls an external contract in the same transaction without updating its state beforehand. An attacker can exploit this vulnerability by calling a malicious contract that triggers a reentrancy attack, causing the original contract to send unexpected amounts of Ether to the attacker's address.

The "unexpected ether" vulnerability is actually a type of re-entrancy attack. A malicious contract takes advantage of a vulnerable contract with a recursive call pattern. The malicious contract calls the vulnerable contract and recursively calls itself before the vulnerable contract can complete its execution. This allows the malicious contract to repeatedly withdraw ether from the vulnerable contract, leading to unexpected ether balance reductions. The malicious contract "re-enters" the vulnerable contract multiple times, exploiting its recursive call pattern.

Real-World Example:

****EtherGame.sol****

```solidity
contract EtherGame {
    
    uint public payoutMileStone1 = 3 ether;
    uint public mileStone1Reward = 2 ether;
    uint public payoutMileStone2 = 5 ether;
    uint public mileStone2Reward = 3 ether; 
    uint public finalMileStone = 10 ether; 
    uint public finalReward = 5 ether; 
    
    mapping(address => uint) redeemableEther;
    // users pay 0.5 ether. At specific milestones, credit their accounts
    function play() public payable {
        require(msg.value == 0.5 ether); // each play is 0.5 ether
        uint currentBalance = this.balance + msg.value;
        // ensure no players after the game as finished
        require(currentBalance <= finalMileStone);
        // if at a milestone credit the players account
        if (currentBalance == payoutMileStone1) {
            redeemableEther[msg.sender] += mileStone1Reward;
        }
        else if (currentBalance == payoutMileStone2) {
            redeemableEther[msg.sender] += mileStone2Reward;
        }
        else if (currentBalance == finalMileStone ) {
            redeemableEther[msg.sender] += finalReward;
        }
        return;
    }
    
    function claimReward() public {
        // ensure the game is complete
        require(this.balance == finalMileStone);
        // ensure there is a reward to give
        require(redeemableEther[msg.sender] > 0); 
        redeemableEther[msg.sender] = 0;
        msg.sender.transfer(redeemableEther[msg.sender]);
    }
 }
view rawEtherGame.sol hosted with ❤ by GitHub
```

*“This contract represents a simple game (which would naturally invoke [race-conditions](https://github.com/sigp/solidity-security-blog#race-conditions)) whereby players send `0.5 ether`quanta to the contract in hope to be the player that reaches one of three milestones first. Milestone's are denominated in ether. The first to reach the milestone may claim a portion of the ether when the game has ended. The game ends when the final milestone (`10 ether`) is reached and users can claim their rewards.*

*The issues with the `EtherGame` contract come from the poor use of `this.balance` in both lines [14] (and by association [16]) and [32]. A mischievous attacker could forcibly send a small amount of ether, let's say `0.1 ether` via the `selfdestruct()`function (discussed above) to prevent any future players from reaching a milestone. As all legitimate players can only send `0.5 ether` increments, `this.balance` would no longer be half integer numbers, as it would also have the `0.1 ether`contribution. This prevents all the if conditions on lines [18], [21] and [24] from being true.*

*Even worse, a vengeful attacker who missed a milestone, could forcibly send `10 ether` (or an equivalent amount of ether that pushes the contract's balance above the `finalMileStone`) which would lock all rewards in the contract forever. This is because the `claimReward()` function will always revert, due to the require on line [32] (i.e. `this.balance` is greater than `finalMileStone`).”*

Source: [https://medium.com/hackernoon/hackpedia-16-solidity-hacks-vulnerabilities-their-fixes-and-real-world-examples-f3210eba5148](https://medium.com/hackernoon/hackpedia-16-solidity-hacks-vulnerabilities-their-fixes-and-real-world-examples-f3210eba5148)

Mitigation

This vulnerability typically arises from the misuse of `this.balance`. Contract logic, when possible, should avoid being dependent on the exact values of the balance of the contract because it can be artificially manipulated. If applying logic based on `this.balance`, ensure to account for unexpected balances.

If exact values of deposited ether are required, a self-defined variable that gets incremented in payable functions should be used to track the deposited ether safely. This variable will not be influenced by the forced ether sent via a `selfdestruct()` call.

With this in mind, a corrected version of the `EtherGame` contract could look like this:

```solidity
contract EtherGame {
    
    uint public payoutMileStone1 = 3 ether;
    uint public mileStone1Reward = 2 ether;
    uint public payoutMileStone2 = 5 ether;
    uint public mileStone2Reward = 3 ether; 
    uint public finalMileStone = 10 ether; 
    uint public finalReward = 5 ether; 
    uint public depositedWei;
    
    mapping (address => uint) redeemableEther;
    
    function play() public payable {
        require(msg.value == 0.5 ether);
        uint currentBalance = depositedWei + msg.value;
        // ensure no players after the game as finished
        require(currentBalance <= finalMileStone);
        if (currentBalance == payoutMileStone1) {
            redeemableEther[msg.sender] += mileStone1Reward;
        }
        else if (currentBalance == payoutMileStone2) {
            redeemableEther[msg.sender] += mileStone2Reward;
        }
        else if (currentBalance == finalMileStone ) {
            redeemableEther[msg.sender] += finalReward;
        }
        depositedWei += msg.value;
        return;
    }
    
    function claimReward() public {
        // ensure the game is complete
        require(depositedWei == finalMileStone);
        // ensure there is a reward to give
        require(redeemableEther[msg.sender] > 0); 
        redeemableEther[msg.sender] = 0;
        msg.sender.transfer(redeemableEther[msg.sender]);
    }
 }
view rawEtherGame.sol hosted with ❤ by GitHub
```

*Here, we have just created a new variable, `depositedEther`
 which keeps track of the known ether deposited, and it is this variable to which we perform our requirements and tests. Notice, that we no longer have any reference to `this.balance.`“*

Mitigating the "Unexpected Ether" vulnerability involves ensuring that smart contracts are designed to update their own state before calling any external contracts in the same transaction. This can be done by using the "checks-effects-interactions" pattern, which involves first checking that all the conditions for the transaction are met, then updating the contract's state, and finally interacting with external contracts. Additionally, developers should ensure that their contracts have proper access control mechanisms in place to prevent unauthorized access to the contract's funds. By following these best practices, developers can significantly reduce the risk of unexpected ether attacks in their smart contracts.

---