# Sybil Attack

Category: Smart Contract Vulnerabilities
Tags: Impact

## What is Sybil Attack?
Sybil attacks occur when large amounts of nodes are created in an attempt to disrupt a P2P(peer-to-peer) network operation by hijacking or dropping messages. The nodes created are pseudonymous identities that gain disproportionately large influence in the network. Sybil attacks typically occur on blockchains that operate on PoS(Proof-of-Stake) consensus mechanism.


## The Tor attack in 2014:
Tor is the earliest evidence of a Sybil attack on a P2P blockchain network. Tor, by design, is a P2P network that enables private messaging. During the attack, the hacker gained controlled about 115 relays from a single IP address. Moreover, similar to a 51% attack, the attacker was able to gain a significant influence over the network.


## Mitigations
Following are some options to mitigate the Sybil Attacks:
- Consider PoW(Proof-of-work) consensus framework (computational power is too large for a Sybil attack to be deployed)
- Implement a storage node reputation system that involves a prolonged initial vetting period that nodes must complete before they are trusted with significant amounts of data or membership
- Determine the similarity between two relay descriptors to discover if those relay descriptors run the same operator.
- Implementation of a relay monitoring system.

## Reference
- [Imperva: Sybil Attack](https://www.imperva.com/learn/application-security/sybil-attack/)
- [Protecting the Tor network from Sybil attacks
](https://petsymposium.org/2015/papers/winter-sybil-hotpets2015.pdf)
- [Sybil Attack in Blockchain: Examples & Prevention](https://hacken.io/insights/sybil-attacks/)
