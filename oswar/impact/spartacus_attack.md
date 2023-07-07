# Spartacus Attack

Category: Smart Contract Vulnerabilities
Tags: Impact

## What is Spartacus Attack?
A Spartacus attack is synonymous with “identity hijacking.” A node assumes the identity of another node, intercepting the messages sent to the intended receiver node. The attack node simply copies the intended receiver node ID.



## Mitigations
Following are some options to mitigate the Sybil Attacks:
- Implementing node IDs as public key hashes and requiring messages to be signed
- Disable the attacker’s ability to generate a corresponding private key owned by the intended receiver node to prevent transactions from being signed
- Node IDs implemented as ECDSA public key hashes


## Reference
- [A Balanced Trust-Based Method to Counter Sybil and Spartacus Attacks in Chord](https://www.hindawi.com/journals/scn/2018/4963932/)
- [Security analysis of blockchain technology](https://www.theseus.fi/bitstream/handle/10024/169305/Security%20analysis%20of%20blockchain%20technology.pdf?sequence=2&isAllowed=y)
- [A Comprehensive Survey on Blockchain-Based Decentralized Storage Networks
](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=10026822)
