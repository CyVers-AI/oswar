# 5.12 Denial of Service (DoS)

Tags: Execution

What is Denial of Service attacks?

A denial of Service (DoS) attack is a type of cyber attack that aims to disrupt the normal functioning of a website or network by overwhelming it with a flood of traffic or requests, rendering it inaccessible to legitimate users. In the context of web3, DoS attacks can take several forms, including DoS with (Unexpected) revert and DoS with Block Gas Limit.

DoS with (Unexpected) revert occurs when an attacker intentionally triggers a function to fail with a revert message, which causes the transaction to consume all the gas allocated to it without achieving its intended purpose. As a result, the remaining transactions in the block fail to execute, leading to a denial of service. This attack can also be launched by exploiting vulnerabilities in the contract code, which allows the attacker to consume all the gas in the block without providing any value to the network.

DoS with Block Gas Limit is a type of DoS attack where an attacker exploits the block gas limit to consume more resources than required, thereby preventing other transactions from being processed. The attacker can achieve this by either submitting transactions with high gas prices or creating many transactions that consume more gas than the block limit.

Distributed Denial of Service (DDoS) is another DoS attack involving the attacker controlling multiple devices to launch an attack on the target node.

The attacker observes the target node and channels the multiple devices under his control to send a large amount of information, flooding the target node. This makes the target crash and unable to fulfill the specified task.

Example:

Ethereum experienced a DDoS attack, where transactions were “spamming” the network. *“Ethereum developers are hard at work on a patch, and the attack already costs the hacker about [$4.50 per minute](https://www.reddit.com/r/ethtrader/comments/53xt58/daily_discussion_22sep2016/d7xk6qf). The attack was successful insofar as it slowed down transactions and made the price of ether drop, but other than that, the network is proving resilient.”*

Source: [https://www.inverse.com/article/21310-ethereum-ddos-cryptocurrency-hackers](https://www.inverse.com/article/21310-ethereum-ddos-cryptocurrency-hackers)

Mitigation:
There are several ways to mitigate DoS attacks in web3. First of all, it depends on what is being attacked. It can be a blockchain network in itself, like the example. It can also be a simple website experiencing a DoS attack due to bots spamming the website and causing a server overload. This is usually prevented with Captcha-like limitations. 

Developers can implement rate-limiting techniques, such as limiting the number of requests per second, to prevent attackers from flooding any network with requests. Network-level solutions, such as load balancers and firewalls, can also be implemented to filter out malicious traffic and prevent DoS attacks. 

It is also essential to monitor traffic to spot irregularities.