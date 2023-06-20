# 5. Coinjoin transaction

Category: Money Laundering

Tags: Defense Evasion

**What is "Coinjoin transaction"?**

CoinJoin is a trustless method used to combine multiple Bitcoin payments from different spenders into a single transaction. This makes it more challenging for outside parties to determine which spender paid which recipient(s). CoinJoin transactions do not require any modification to the Bitcoin protocol itself​.

In a typical Bitcoin transaction, one or more inputs are consumed to create one or more outputs with specified values. Each input is an output from a past transaction and has a unique signature. It is common for a transaction to use multiple inputs to accumulate enough value for its intended payment, often also creating an additional 'change' output for any unspent excess. There is no requirement for these inputs to be payments to the same address. In fact, when Bitcoin is used correctly with one address per payment, none of the inputs will be the same​​.

CoinJoin works on the principle that the signatures inside a transaction are entirely independent of each other. This allows Bitcoin users to agree on a set of inputs to spend and a set of outputs to pay, then individually and separately sign a transaction and later merge their signatures. The transaction is not valid and won't be accepted by the network until all signatures are provided. No one will sign a transaction which is not to their liking, thus there is no risk of theft at any point​​.

CoinJoin can also be used more casually. For example, when you want to make a payment, you can find someone else who also wants to make a payment and make a joint payment together. This doesn't significantly increase privacy, but it makes the transaction smaller, which is easier on the network and lower in fees. The additional privacy is a bonus. Such transactions are externally indistinguishable from transactions created through conventional use. If these transactions become widespread, they can improve privacy even for people who do not use them, as the co-joining of inputs will no longer be strong evidence of common control. There can be many variations of this concept, and all can coexist because the idea requires no changes to the Bitcoin system​​.

**CoinJoin-supported wallets**

 - Samourai
 - Sparrow 
 - Wasabi 
 - Jam
 - Apirone

**Example**

Let's say Alice and Bob want to make Bitcoin payments. Alice wants to send 1 Bitcoin (BTC) to her friend Charlie, and Bob wants to send 1 BTC to his friend Dave. Rather than making these transactions separately, they use CoinJoin to make a joint payment.

1. Alice and Bob agree on the inputs and outputs for the transaction. Alice provides an input of 1 BTC from her address, and Bob provides an input of 1 BTC from his address. For the outputs, they agree on two separate outputs of 1 BTC each, one for Charlie and one for Dave.

2. Alice and Bob then separately sign a transaction with these inputs and outputs. Alice's signature authorizes the use of her 1 BTC input and designates Charlie as the recipient of one of the 1 BTC outputs. Bob's signature does the same for his 1 BTC input and designates Dave as the recipient of the other 1 BTC output.

3. After both Alice and Bob have signed the transaction, their signatures are merged to form a complete transaction that can be submitted to the Bitcoin network.

The resulting transaction looks like a single transaction that spends 2 BTC and has two 1 BTC outputs. However, it is not clear from the transaction itself which of the 1 BTC inputs is intended for Charlie and which is for Dave. This obscures the link between the inputs and outputs, enhancing the privacy of the transaction.

Please note that in real-world usage, CoinJoin transactions often involve more than two participants and can have many inputs and outputs, increasing the privacy benefits. Also, CoinJoin transactions are typically coordinated through software or services designed to facilitate the process, to handle the complexities of managing inputs, outputs, and signatures.

**Mitigation**

 - Heuristics based on transaction patterns: Some blockchain analysis techniques rely on heuristics, or rules of thumb, based on common patterns seen in CoinJoin transactions. For example, they might look for transactions with a large number of inputs and outputs of the same value, which is a pattern often seen in CoinJoin transactions.

**Reference**

- [CoinJoin](https://en.bitcoin.it/wiki/CoinJoin)

- [MistTrack Case 02: Wasabi Coinjoin Withdrawal Analysis](https://slowmist.medium.com/misttrack-case-study-ii-wasabi-coinjoin-withdrawal-analysis-a3879a59cf4)

- [The Unique Dressing of Transactions: Wasabi CoinJoin Transaction](https://pure.hw.ac.uk/ws/portalfiles/portal/55850474/TirMaaEroJus_EICC_2022_camera_ready.pdf)
