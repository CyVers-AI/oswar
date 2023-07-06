# 4. Guardian takeover

Category: Higher Privilige Attacks
Tags: Privilege Escalation

### What is a “Guardian takeover”?

A guardian takeover attack is a type of attack in which a hacker gains control of the guardian account for a decentralized application (dApp). This enables them to manipulate the smart contract that governs the dApp's operations and have complete control over the dApp. Such an attack can lead to theft of funds, modification of the contract's rules, or a complete shutdown of the dApp.

In a dApp, a guardian is a designated party responsible for managing the smart contract that governs the dApp's operations. A guardian takeover attack occurs when a hacker gains control of the guardian account, allowing them to manipulate the smart contract and have complete control over the dApp. Once they have control, they can potentially steal funds, modify the contract's rules in their favor, or shut down the dApp entirely.

### Example:

The Ronin Network hack of 2022 serves as an example of a Guardian Takeover attack.

The Axie Infinity blockchain gaming application gained a lot of popularity and was developed on the Ronin Network. Unfortunately, Ronin suffered one of its worst hacks in March 2022, when a malicious actor was able to quickly obtain 173,600 ether ($ETH) and 25.5 million USDC, which were later exchanged for $625 million. The hacker managed to get hold of the necessary private keys and consequently stole all the funds from the Ronin Bridge in just two transactions, making it one of the most significant DeFi breaches to date.

The Ronin Bridge was operated by nine "validators," with a five out of nine threshold. Sky Mavis (the company behind Axie Infinity) oversaw four validators, so the private keys weren't distributed enough. Furthermore, Axie delegated their validator's signature to Sky Mavis in November 2021. Although this delegation was supposed to be temporary because Axie was experiencing heavy traffic, it was never revoked. Sky Mavis ended up with five validator signatures, enough to approve any message. Through a social-engineering attack, the attacker obtained control of the keys. They could call withdrawERC from the bridge without a backing transaction on the other side once they had the keys.

### Mitigation:

Decentralization is a crucial feature of all dApps. This makes it more challenging for a single entity to gain control of the network. But the access points to get control of the dApp can still be exploited or compromised. To prevent guardian takeover attacks, strong security measures are required, including:

- Proper access controls: Implementing proper access controls for guardians and validators can help prevent unauthorized access to sensitive areas of the dApp, reducing the risk of attacks.
- Regular security audits: Conducting regular security audits can help identify vulnerabilities in the dApp's code and infrastructure, allowing for them to be addressed before they can be exploited.
- Multi-signature authorization: Implementing multi-signature authorization can help prevent guardian takeover attacks by requiring multiple parties to authorize certain actions, such as fund transfers or changes to the smart contract.
- Emergency protocols: Implementing emergency protocols can help prevent or mitigate the impact of attacks by allowing for quick action in the event of an attack.
- Real-time monitoring: Implementing proactive security measures such as real-time monitroing is essential to be alerted int eh case of a potential attack.

In summary, preventing guardian takeover attacks requires strong security measures, including decentralization, robust consensus mechanisms, proper access controls, regular security audits, multi-signature authorization, and emergency protocols. By taking a comprehensive approach to security, it is possible to reduce the risk of attacks and protect the integrity of the dApp.