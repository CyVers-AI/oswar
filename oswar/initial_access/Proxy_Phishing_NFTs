# 2. Proxy Phishing NFTs

Category: User Target 
Tags: Initial Access

### What is "OpenSea OwnableDelegateProxy Phishing"?

OpenSea OwnableDelegateProxy phishing is a form of cybersecurity threat, specifically a phishing attack, which targeted users of the OpenSea marketplace. It primarily affected users who had listed Non-Fungible Tokens (NFTs) using the legacy Wyvern Protocol.

Wyvern Protocol, in combination with WyvernProxyRegistry, created the OwnableDelegateProxy. This Delegate Proxy is a type of Ethereum smart contract that users interact with when they engage in buying or selling NFTs on OpenSea. When a user lists an NFT for sale, they delegate authority to this contract to withdraw their NFTs to facilitate order matching.

### Example

The phishing attack took advantage of this process by deceiving users into signing a transaction that seemingly appeared routine, but in actuality transferred the ownership of their Delegate Proxy contract to the attacker via the **"upgradeTo()"** function. Once the attacker assumed control of the Delegate Proxy, they had the ability to withdraw NFTs directly from the victim's wallet. This exploit was notably prevalent for NFTs listed on OpenSea before May 2022, which is when OpenSea transitioned from the Wyvern Protocol to its newer Seaport Protocol.
However, a minority of users are still using the old contract [WyvernProxyRegistry](https://etherscan.io/address/0xa5409ec958c83c3f309868babaca7c86dcb077c1) to create accounts.

### Mitigation

Users are advised to exercise caution before signing any transactions and to thoroughly verify the details of each transaction. Additionally, it is recommended to revoke permissions to the old OpenSea contract via platforms such as Revoke.cash, to limit potential exposure to this form of attack.

### Reference
- [2 BYAC hacked by signing a malicious Opensea OwnableDelegateProxy upgrade transaction](https://twitter.com/realScamSniffer/status/1666258509221216257)
