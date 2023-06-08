# 2. Rugpull

Category: Malicious Deployment
Tag: Persistence

###  What is a Rugpull?
A rugpull is a type of scam in the cryptocurrency and DeFi (Decentralized Finance) space where project developers abruptly pull the plug on their project and abscond with the users’ funds. This usually involves the manipulation of smart contracts or other mechanisms in a DeFi protocol. Once the rugpull occurs, users are left with worthless tokens and no means to recover their funds.
The name “rugpull” comes from the metaphor of a rug being pulled out from under a person, implying a sudden and unexpected action that leaves the victim off balance and helpless.

### Case Study of Kokomo Finance Exploit
On March 27, 2023, Kokomo Finance, a lending protocol on the Optimism blockchain, performed a rugpull and disappeared with approximately $4 million worth of tokens, mostly in the form of Wrapped Bitcoin (WBTC). The exploit involved a malicious contract modification made by the project’s deployer address, which rugged Wrapped Bitcoin deposits. Shortly after the rugpull, the project’s online presence, including its website, Twitter, GitHub, and Medium, was deleted.
The steps to reproduce the exploit, as well as transaction analysis and identified rugpull indicators, are described above.

## Rugpull according to STRIDE and MITRE
This exploit can be categorized according to the STRIDE (Spoofing, Tampering, Repudiation, Information Disclosure, Denial of Service, and Elevation of Privilege) model and the MITRE ATT&CK (Adversarial Tactics, Techniques, and Common Knowledge) framework as follows:
- **STRIDE Category**: `Tampering`. The attacker modified the smart contract to redirect WBTC to their own address.
- **MITRE ATT&CK Tactic**: `Impact`. The attacker’s goal was to cause financial loss to the users of the protocol and drain all the funds.
- **MITRE ATT&CK Technique**: Endpoint Denial of Service (T1499). By modifying the smart contract, the attacker effectively made the protocol unavailable for legitimate users to withdraw their funds. 
- Many a times it is noticed that the attackers used upgradable proxies and admin functions to make external calls to a malicious contract controlled by them & drain complete funds from the protocols vault. 

## Mitigation
Preventing rugpulls can be challenging due to the decentralized and permissionless nature of DeFi. However, there are several measures that can be taken to mitigate the risk of rugpulls:
- **Anonymous or unknown team** : 
A team that is anonymous or unknown should be a red flag as they may not have any reputation to uphold and can disappear easily.

- **Unaudited code** : 
A smart contract that has not been audited or reviewed by reputable third-party auditors increases the risk of vulnerabilities and potential exploits.

- **Centralized control**: 
A smart contract that gives excessive control to the owner or a small group of individuals can lead to potential misuse of funds or a rugpull.

- **Lack of transparency**: 
A rugpull often involves a lack of transparency or information on the project, such as unclear tokenomics or a lack of information on the team or project roadmap.

- **Unrealistic promises**: 
Projects that make unrealistic promises of high returns or quick profits without a clear explanation of how these returns will be generated should be approached with caution.

- **Lack of liquidity**: 
If a project has low liquidity or a small number of holders, it may be easier for a rugpull to occur as there may not be enough holders to prevent a large-scale dump.

- **Sudden changes or delays**: 
A sudden change in the project roadmap or significant delays in project milestones without proper communication to investors can be a warning sign of a potential rugpull.

### Reference: 
https://rekt.news/kokomo-finance-rekt/
