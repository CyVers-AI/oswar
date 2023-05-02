# 4. Validator Priviliges

Tags: Initial Access

### What are Validator Privileges?

Validator privileges refer to elevated access and control validators have in a blockchain network or protocol. Validators are responsible for validating transactions, creating new blocks, and maintaining the integrity of the blockchain. They can also be given extra privileges, such as updating the price of an oracle or staking several tokens. As a result, they have privileged access to the network and can potentially exploit vulnerabilities to gain unauthorized access or execute attacks.

### **Example**

The BonqDAO hack is a prime example of how attackers can exploit validator privileges to execute attacks. The attacker became a validator and updated the price feed for (wrapped) WALBT collateral by staking 10 TRB tokens (worth just ~$175). This allowed the attacker to borrow against inflated collateral in the same transaction, resulting in a significant financial loss for the BonqDAO protocol.

Staking made the hacker a validator with privileged access to update the price. Since a vulnerability enabled the hacker to update the price instantly, the attacker borrowed against the inflated collateral in the same transaction. The attacker used the submit Value function to report the WALBT price to the oracle. The anonymous attacker got away with around $2M. Essentially, the Polygon-based lending and stablecoin protocol BonqDAO was hit by a two-stage attack on Wednesday in another example of oracle manipulation.

- Another hack that included validator access occurred in the Binance bridge hack in 2022.

### **Mitigation**

To mitigate these risks, consider the following measures:

- Implement strict access controls: Limit access to validator nodes by stricter criteria, even if this results in less decentralization.
- Implement continuous monitoring and logging: This allows security teams to detect suspicious activity and respond quickly to potential threats. It is essential to monitor all network activity, including validator nodes, and log all events, including authentication attempts, network traffic, and system events.
- Implement smart contract best practices: Smart contracts are one of the most vulnerable components of a blockchain network. It is essential to follow best practices to reduce the risk of vulnerabilities. This includes using well-audited smart contract libraries, limiting complex logic in smart contracts, and ensuring that all code is thoroughly tested and audited.
- Conduct regular security audits and penetration testing: This involves testing the network for vulnerabilities and identifying potential attack vectors. Independent third-party security firms should conduct security audits and penetration testing to identify and address all potential vulnerabilities.
- Implement security protocols for cross-chain transactions: Cross-chain transactions can be especially vulnerable to attacks, and it is essential to implement security protocols to protect against these attacks. This includes using secure communication protocols, validating transaction signatures, and implementing time-locking mechanisms to prevent attackers from exploiting vulnerabilities in one chain to attack another.
- 

Source:  [https://rekt.news/bonq-rekt/](https://rekt.news/bonq-rekt/)