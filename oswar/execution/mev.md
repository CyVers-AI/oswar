# 3. MEV

Category: User Target
Tags: Execution

## What is MEV?

MEV (Maximal Extractable Value) refers to identifying and taking advantage of opportunities created by the order in which transactions are processed within a block.

For example, consider a decentralized exchange (DEX) that uses an automated market maker (AMM) algorithm to determine the price of a cryptocurrency. When a trader wants to swap one token for another on this DEX, they send a transaction processed by the AMM and the blockchain. However, several other traders may also attempt to take advantage of the same price movements by submitting transactions simultaneously while carefully monitoring other traders. In this scenario, the order in which the transactions are included in the block is crucial in determining which trader's transaction is executed first and who ultimately profits from the transaction.

## Example:

Imagine a DeFi lending protocol where users can borrow funds by collateralizing their cryptocurrency holdings. If the value of this collateral drops below a certain threshold, the protocol can liquidate the collateral to recover the borrowed funds. A trader observing the blockchain for these liquidation events can submit a transaction that buys up the liquidated assets at a discount before other traders can react and then sell them for a profit.

In this scenario, the MEV opportunity arises from the order of transactions in the block rather than by manipulating the transaction pool through front-running.

## Mitigation:

MEV (Miner Extractable Value) exploits refer to a type of attack on a blockchain that allows miners to manipulate transaction orders and potentially profit at the expense of other users. Here are some ways to prevent MEV exploits:

- Use an MEV protection tool: Tools such as Flashbots can help protect against MEV exploits by allowing users to bundle their transactions and communicate directly with miners. This reduces the incentive for miners to engage in MEV exploits.
- Implement transaction fee caps: Users can limit the profit miners make from MEV exploits by setting caps on transaction fees. This can be done by implementing fee market protocols
- Use privacy-preserving technologies: MEV exploits often rely on the ability to track transactions and manipulate their order. By implementing privacy-preserving technologies such as zk-SNARKs, transactions can be made more private and less susceptible to manipulation.
- Implement transaction finality: MEV exploits often rely on the ability to manipulate transaction order. By implementing transaction finality, transactions become irreversible and less susceptible to manipulation.
- Use decentralized exchanges: Decentralized exchanges (DEXs) can help prevent MEV exploits by eliminating the need for transaction ordering. By using a DEX, transactions are settled in a trustless manner, reducing the risk of MEV exploits.

It is important to note that preventing MEV exploits is an ongoing challenge in the blockchain space, and new solutions may emerge over time. Users need to stay informed and vigilant against potential threats to their transactions.

Sources: [https://flashbots.net/](https://flashbots.net/)

[https://flashbots.net/](https://flashbots.net/)

[https://www.coindesk.com/what-is-mev-crypto](https://www.coindesk.com/what-is-mev-crypto)

[https://www.coindesk.com/what-is-mev-crypto](https://www.coindesk.com/what-is-mev-crypto)

[https://www.coindesk.com/what-is-mev-crypto](https://www.coindesk.com/what-is-mev-crypto)