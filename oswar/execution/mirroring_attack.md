# Mirroring Attack

Category: Oracle / AMM
Tags: Execution

## What is Mirroring Attack?
This attack simply put, is a collusion between data feeders. A mirroring attack occurs when a node reads from a centralized data source and then duplicates its content across participants who mirror that data. As the number of mirroring participants grows, this increased weight on a single data point can significantly deteriorate error correction mechanisms.

## Mitigations
Following are some options to mitigate the Mirroring Attacks:
- Leverage a censorship-resistant oracle that is decentralized by nature, making data public and visible
- Decentralized oracles: Chainlink, Tellor, Witnet, and Redstone Finance
- Utilization of multiple different oracles
- Don’t rely on commit-reveal schemes
- Ensure the confidentiality of data sent by the data feeders

Mirroring attacks are very hard to detect but don’t fret. The best practice a protocol can implement is using various different oracles in case one fails. It’s worth the gwei in some cases.

## Reference
- [RedStone Finance](https://docs.redstone.finance/docs/introduction)
- [Chainlink](https://chain.link)
- [Tellor](https://tellor.io)
- [Witnet](https://witnet.io)
- [Consensys: Oracle Manipulation](https://consensys.github.io/smart-contract-best-practices/attacks/oracle-manipulation/)
- [SoK: Oracles from the Ground Truth to Market Manipulation](https://arxiv.org/pdf/2106.00667.pdf)
