# 1. API Discovery

Tags: Discovery

## What is "API Discovery"?

After gaining initial access to a dApp, an attacker may attempt to discover its underlying infrastructure, such as connected backend services, databases, or APIs. API Discovery is a technique adversaries use to identify and enumerate Application Programming Interfaces (APIs) exposed by blockchain nodes or decentralized applications (dApps). These APIs interact with the blockchain network and perform various tasks, such as submitting transactions, querying data, or monitoring events. Adversaries can use multiple techniques to discover and enumerate these APIs, such as scanning the network, analyzing the source code of smart contracts or dApps, or using specialized tools designed for API discovery. Once vulnerable or misconfigured APIs are identified, adversaries can exploit them to gain unauthorized access to sensitive data or disrupt the network.

### Example:

An example of this is the FTX collapse. External sources have cited that unauthorized access to API keys was one of the reasons for the hack and subsequent collapse.

### Mitigation:

To reduce the risks associated with API discovery, blockchain developers and organizations can take the following measures:

1. Implement Access Controls: Ensure that APIs are protected with authentication and access controls, like API keys or OAuth tokens. This will help prevent unauthorized access to sensitive data or functions.
2. Monitor API Activity: Keep a close eye on API activity, and log all requests and responses to detect suspicious or unauthorized behavior. This will help identify potential attacks and provide forensic evidence in case of a breach.
3. Regularly Update and Patch: Keep APIs up-to-date, and patch them to address known vulnerabilities and misconfigurations. This will help reduce the attack surface and prevent the exploitation of known weaknesses.
4. Use Security Tools: Use specialized security tools designed for API discovery and vulnerability scanning, like Nmap, Burp Suite, or ZAP, to identify and fix vulnerabilities in blockchain APIs. These tools can also help validate access controls' effectiveness and identify potential API implementation weaknesses.

Source: [https://beincrypto.com/ftx-users-lose-millions-to-api-exploit/](https://beincrypto.com/ftx-users-lose-millions-to-api-exploit/)