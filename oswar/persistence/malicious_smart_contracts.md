# 3. Malicious Smart Contracts

Category: Malicious deployment
Tags: Persistence

What are “Malicious Smart Contracts”?

Malicious smart contracts are code deployed on a blockchain platform that contains harmful functions or vulnerabilities. These contracts are designed to exploit weaknesses in dApps or the blockchain, performing unauthorized actions or causing unintended consequences. Once deployed, malicious smart contracts persist on the blockchain, allowing attackers to maintain control over the affected dApps or extract value from unsuspecting users. In this attack, an attacker injects malicious code into a smart contract or decentralized application. The code can be designed to steal funds, modify or destroy the contract, or execute other malicious actions. Once injected, the code can persist and execute even if the contract is upgraded or migrated.

Malicious smart contracts are a growing concern in the Web3 ecosystem, as they can enable attackers to exploit vulnerabilities in decentralized applications (dApps) or blockchain platforms. These attacks can result in stolen funds, manipulated data, or disrupted operations. Due to their nature, malicious smart contracts are best placed under the "Persistence" tactic in the MITRE ATT&CK framework. They maintain their presence on the blockchain and can continuously execute malicious functions when triggered.

Examples

Reentrancy attacks: The infamous DAO hack of 2016 is an example of a reentrancy attack where an attacker exploited a vulnerability in The DAO's smart contract, continuously withdrawing funds before the attack was detected and stopped.

Scams and phishing attacks: In the OpenSea phishing attack of February 2022, users were tricked into signing a malicious smart contract that transferred their NFTs to a hacker's address.

Flash loan attacks: In these attacks, hackers deploy malicious smart contracts that enable them to borrow and manipulate large amounts of cryptocurrency within a single transaction, exploiting vulnerabilities in decentralized finance (DeFi) platforms.

A famous example of one of these crypto smart contract scams was the $1.7m February 2022 [OpenSea phishing attack](https://medium.com/harpie-io/1-7m-stolen-from-simple-email-phishing-3-essential-takeaways-from-the-opensea-attack-9d6fa7dbd363).

![https://miro.medium.com/v2/resize:fit:1400/0*AKlQ6VZ4V7C6EYhE.png](https://miro.medium.com/v2/resize:fit:1400/0*AKlQ6VZ4V7C6EYhE.png)

By opening up this phishing email, users were asked to sign a malicious smart contract that transferred all their NFTs to a hacker’s address. This is a user-specific incident. 

In many hacks, like flashloans, the hacker deploys malicious smart contracts, which enable the exploiter to execute transactions automatically. 

Other malicious smart contract examples are when the hacker interacts with DApps and/or protocol logic and exploits the vulnerability, tricking the smart contracts into thinking his malicious ones are real and original. 

Another real-world example is the ****PAID Network,**** where the hack involved a malicious smart contract. Analysis to be found here:
[https://cryptoshine.medium.com/paid-contract-hack-deep-dive-4dd89e1414f5](https://cryptoshine.medium.com/paid-contract-hack-deep-dive-4dd89e1414f5)

Mitigation:

To protect against malicious smart contracts, it is crucial to follow best practices for secure smart contract development and deployment. Some key strategies include:

Security reviews and testing: Perform thorough security audits, code reviews, and testing to identify vulnerabilities in smart contracts before deployment. This can help prevent the introduction of malicious code or exploitable weaknesses.

Implement access controls: Use access controls to restrict who can modify or interact with smart contracts, reducing the likelihood of unauthorized changes or exploitation.

Secure coding practices: Follow secure coding practices, such as input validation, sanitization, and proper error handling. Be aware of common smart contract vulnerabilities, like reentrancy attacks, and implement safeguards to mitigate them.

Monitoring and response: Implement real-time monitoring and automated alert systems to detect suspicious activity, such as unexpected changes to contract code or anomalous transaction patterns. Swiftly respond to identified threats to limit potential damage.

Education and awareness: Educate developers, users, and stakeholders about the risks associated with malicious smart contracts and the importance of following best practices for smart contract security.

By focusing on persistence and implementing these mitigation strategies, the Web3 ecosystem can better protect itself against the threat of malicious smart contracts and ensure the security of decentralized applications and blockchain platforms.

Proactive and real-time monitoring. 

Real-time monitoring can be a powerful tool in preventing the deployment of malicious contracts in web3. Monitoring smart contracts and dApps in real-time makes it possible to detect and respond to suspicious activity before it can cause harm. Here are some ways that real-time monitoring can help prevent the deployment of malicious contracts:

1. Detecting anomalous behavior: Real-time monitoring can help detect anomalous behavior in smart contracts and dApps. For example, sudden changes in transaction volume or activity patterns can indicate that a contract has been compromised or that an attacker is attempting to inject malicious code.
2. Identifying vulnerabilities: Real-time monitoring can help identify vulnerabilities in smart contracts and dApps. By identifying potential attack vectors and vulnerabilities, it is possible to address them before attackers can exploit them.
3. Alerting security teams: Real-time monitoring can provide real-time alerts when suspicious activity is detected. This can allow teams to respond quickly and prevent the deployment of malicious contracts or dApps.
4. Tracking changes: Real-time monitoring can track changes to smart contracts and dApps, allowing for a detailed audit trail of activity. This can help identify the source of a potential attack and provide valuable information for incident response and forensics.
5. Automated response: Real-time monitoring can also trigger automated responses when suspicious activity is detected. For example, an automated response might include disabling the contract or blocking certain types of transactions until the security team can investigate further.

In summary, real-time monitoring can help prevent the deployment of malicious contracts by providing early detection and alerting of suspicious activity, identifying vulnerabilities, tracking changes, and triggering automated responses. By combining real-time monitoring with other security best practices, such as secure coding and access controls, it is possible to create a comprehensive security strategy to help protect against a wide range of attacks in web3.