# 4. Oracle attack

Category: Oracle / AMM
Tags: Execution

## What is an Oracle Attack?

An Oracle is a trustworthy third-party data source that a smart contract can use to obtain external information. Oracle attacks involve manipulating the Oracle to provide false or malicious data to the smart contract or any party depending on the data. This can result in unauthorized access, theft of cryptocurrency, or even liquidation events.

One type of Oracle attack is incorrect or insecure validation, where malicious actors can manually change the price of an Oracle by exploiting vulnerabilities in the validation process. This allows them to provide inaccurate data to the smart contract, which can cause financial losses or unauthorized access.

### Example

A similar hack occurred with BonqDAO. According to reports, the hacker gained access to the Tellor price feed for (wrapped) WALBT collateral by staking 10 TRB tokens, which were valued at approximately $175. [source](https://rekt.news/bonq-rekt/)

Another instance is the compound oracle liquidation event, in which Coinbase's DAI stablecoin oracles were susceptible to spoofing and oracle manipulation. [source](https://news.bitcoin.com/100-million-liquidated-on-defi-protocol-compound-following-oracle-exploit/)

Oracle attacks can vary between decentralized and centralized exchanges. Oracles are frequently centralized entities, making them a single point of failure. In such cases, an Oracle attack can result in market data manipulation, leading to market distortions and financial losses. One example is spoofing, which involves executing false orders to manipulate prices and the perception of price action.

In decentralized exchanges, the most common types of "Oracles" are Automated Market Makers (AMMs) and Order Books. With the AMM model, attackers can manipulate the price of tokens by exploiting liquidity imbalances using flash loans. This can lead to significant market distortions, causing financial losses for traders. On the other hand, with the Order Book model, attackers can manipulate the order books to falsely represent supply and demand, resulting in significant market distortions and financial losses. Although quite distinct, it has its section in the execution list.

### Mitigation

To prevent oracle attacks, it is best to follow secure coding practices such as using multiple independent oracles and drawing a median of the reported price. It is important to thoroughly verify the data and reported price received from the oracle.

Choose a trustworthy oracle: The first step in preventing oracle attacks is to choose a reputable oracle. It is essential to research the oracle thoroughly and verify its reputation.

Use a decentralized oracle network: A decentralized oracle network can add an extra layer of security to your dApp. Decentralized oracle networks ensure data integrity by using multiple oracles to verify the same data. Chainlink oracles are an excellent example of this.