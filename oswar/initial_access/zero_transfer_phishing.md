# 2. Zero Transfer Phishing

Category: User Target
Tags: Initial Access

### What is Zero Transfer Phishing?

Illicit smart contracts generate "transfers" of zero-value tokens from the addresses of victims to fake addresses that resemble those with which the victims had previously interacted. The "transfers" have zero value because they don't actually represent the transfer of any tokens. As a result, they can be processed without the usual consent from the source or the victim's wallet. 

The goal is to deceive the victim into mistakenly being sent to the attacker's fake address rather than the legitimate one they had previously communicated with. How does that function? Because many users frequently examine their transaction history to determine which addresses they have once sent to and copy and paste this address from the most recent transaction the victim submitted to it while setting up a new transaction. And how do the majority of users verify that an address is accurate? To ensure that the wallet address is constant throughout their previous transactions, they will swiftly scan the first and final few characters. They frequently need to evaluate and compare every character.
Scan, Copy, Paste, Theft!

This type of hack is targeted at individuals and EOA wallets. 

### Example

A real-world example and explanation can be found on the Coinbase blog:

[https://www.coinbase.com/blog/zero-transfer-phishing-part-1-attack-analysis](https://www.coinbase.com/blog/zero-transfer-phishing-part-1-attack-analysis)

### Mitigation

To prevent falling for Zero Transfer Phishing, triple-check that the wallet or contract address you are interacting with is correct. Do not only check the last numerals/letters in the address.

As Coinbase mentions in their article, there are other mitigation techniques:

- Verify the entirety of the address before sending. Attackers may have generated a vanity address to resemble a legitimate one closely.
- Be mindful about copying addresses from transactions that you did not originate or that look suspicious. Existing ERC-20 tokens will continue allowing zero transactions to and from arbitrary transactions.
- Use blockchain explorers (e.g., Etherscan) and wallets (e.g., Coinbase Wallet) which flag or filter malicious transactions and addresses.

Blockchain explorers and wallets can implement the following approaches to help shield consumers from this and similar threats:

- Flag or filter transfer events with the value set to 0. Consider derivative exploitation vectors for non-ERC-20 transfer events (e.g. NFTs, staking, etc.).
- Implement address mask collision detection to identify similar addresses unlikely to have been generated randomly (e.g., same N first and last characters).
- If shortening addresses, consider including 3+ bytes on each side to make mass vanity generation harder (e.g. 0x123456...abcdef).
- Alert users on new/unknown addresses when initiating transfers.

---

[Zero Transfer Phishing - Part 1 - Attack Analysis - Blog](https://www.coinbase.com/blog/zero-transfer-phishing-part-1-attack-analysis)