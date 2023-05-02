# 5.26 Check-Effect- Interaction (CEI)

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “Check Effect Interaction”?

"Check-Effect-Interaction" (CEI) is a common pattern used in smart contract development to prevent race conditions and ensure that transactions execute as intended. The CEI pattern involves three steps:

1. Check: The contract checks whether the transaction is valid or not.
2. Effect: If the transaction is valid, the contract executes the intended changes to the contract state.
3. Interaction: The contract interacts with other contracts or external entities, such as sending or receiving funds.

Example:

An example of CEI can be seen in a contract that allows users to withdraw funds. The contract would check that the user has sufficient funds to withdraw, then effect the withdrawal by updating the user's balance, and finally interact with the external entity to send the requested funds to the user's account.

Without CEI, there is a risk of a race condition where two or more transactions attempt to modify the contract state simultaneously, leading to unexpected behavior and potential vulnerabilities.

Mitigation:

To prevent issues related to race conditions, it is essential to follow the CEI pattern when designing and implementing smart contracts. Additionally, contracts should be tested thoroughly to ensure they behave as expected and resist any potential vulnerabilities that may arise from race conditions.