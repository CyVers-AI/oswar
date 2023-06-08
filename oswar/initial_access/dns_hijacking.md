
# 2. DNS Hijacking

Category: Higher Privilege Attacks
Tags: Initial Access

### What is DNS Hijacking?
DNS Hijacking, also known as DNS Redirection, is a form of malicious attack where an attacker alters the DNS (Domain Name System) configuration. The attacker can then redirect the victim to fraudulent websites, often for the purpose of phishing, spreading malware, or stealing sensitive information. DNS is crucial for internet browsing as it translates domain names (like www.example.com) into IP addresses. A DNS hijacking attack can manipulate this process, rerouting a user’s online traffic to potentially harmful destinations.

### Example:
A real-world example of a DNS hijacking attack is the Curve Finance incident that occurred on August 10, 2022. The attackers hijacked the DNS and injected a malicious contract address via JavaScript into the front-end of the Curve Finance protocol, a reputable coin-swapping platform in the decentralized finance (DeFi) sector. This allowed the attackers to reroute users’ funds and approvals from Curve.fi into their own wallets, resulting in a loss of around $575,000 from users’ accounts. Unaware users believed they were interacting with the legitimate Curve Finance platform, but they were actually authorizing transactions that drained their funds.

### Mitigation:
Some of the best practices To mitigate DNS hijacking attacks 
1. Using secure network protocols like HTTPS and DNSSEC (Domain Name System Security Extensions) which provide authentication of DNS data, data integrity, and authenticated denial of existence.
2. Using strong, unique passwords to prevent unauthorized access to routers and other network devices.
3. Enabling two-factor authentication (2FA) for an additional layer of security.

### Reference 
https://rekt.news/curve-finance-rekt/
