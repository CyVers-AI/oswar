# 5. Smart contract vulnerabilities

Tags: Execution

### What are "smart contract vulnerabilities"?

Smart contracts are programs that run automatically on the blockchain and enable trustless agreements without intermediaries. Although they may sound complex, they are just the code behind blockchain applications. If smart contracts are not coded correctly, they may contain vulnerabilities that hackers can exploit to access a Web3 platform. In 2022, 50% of all hacks were due to smart contract vulnerabilities. Even audited projects can have vulnerabilities or logic errors that hackers can exploit and manipulate.

Smart contracts can perform various tasks, such as financial transactions, voting systems, and supply chain management. However, these contracts can have vulnerabilities, and understanding them is crucial to secure the entire Web3 ecosystem.

One critical feature of smart contracts is their immutability. Once deployed on the blockchain, they cannot be modified or deleted. This means the contract code is fixed, and any vulnerabilities will remain until the contract ends.

### Example

Smart contracts can, for example, contain vulnerabilities that allow hackers to access the funds from DApps. These vulnerabilities can arise from various sources, such as flaws in the code, weaknesses in the underlying blockchain network, or manipulation of user inputs to the contract. The consequences of these vulnerabilities can be severe, including loss of funds, theft of sensitive information, or disruption of the entire network.

One common type of vulnerability is the Reentrancy vulnerability, where attackers exploit the ability of smart contracts to call other contracts within their code. By repeatedly calling a vulnerable function in the contract before the previous call has been completed, attackers can withdraw funds multiple times before the contract balance is updated.

Another type of vulnerability is the Integer Overflow and Underflow vulnerability, where attackers manipulate the input data of the smart contract to cause arithmetic operations to overflow or underflow, leading to unintended consequences, such as an attacker receiving more tokens than they should or causing the contract to fail.

The Timestamp Dependency vulnerability is another type of vulnerability where attackers manipulate the timestamp of a smart contract to trick it into executing a function before it is supposed to. This can be used to take advantage of specific conditions that may only exist for a brief period, such as the issuance of a new token. Smart contracts can also be vulnerable to Denial of Service (DoS) attacks, where attackers flood the contract with large numbers of transactions or inputs to overwhelm the contract and prevent legitimate users from interacting.

### Mitigation

To mitigate smart contract vulnerabilities, it is essential to conduct thorough security audits of smart contracts before deploying them on the blockchain. This includes testing the code for known vulnerabilities and running simulations of various attack scenarios to identify potential weaknesses. Additionally, it is necessary to ensure that smart contracts are designed with security in mind from the outset and that developers follow best practices for secure coding. This includes implementing strict input validation checks, using up-to-date libraries and frameworks, and properly documenting the code to ensure that future developers can easily understand how the contract works.

In addition to smart contract auditing, a passive form of mitigating hacks and real-time monitoring of smart contracts and wallets is needed to respond swiftly in the case of an exploit. This more proactive approach gives protocol founders and developers much more versatility in the event of an attack. It gives them a real chance of preventing hacks before they cause devastating damage.

Overall, smart contracts are a powerful tool for enabling trustless automation in Web3, but they are not without vulnerabilities. Developers and users must take steps to ensure the security of these contracts.