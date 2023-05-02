# 5.7 Time manipulation

Category: Smart Contract Vulnerabilities
Tags: Execution

What is Time Manipulation?

Time manipulation is a smart contract vulnerability that allows attackers to exploit a contract by manipulating the timestamps or block numbers. In a blockchain environment, timestamps and block numbers are crucial components of the consensus algorithm that ensures the integrity and immutability of the blockchain. In a smart contract, timestamps and block numbers determine when certain functions should be executed or funds should be unlocked.

An attacker can exploit this vulnerability by manipulating the timestamps or block numbers to trick the contract into unlocking funds before they are supposed to be available or accessing a specific function in the contract at a reasonable time. This can be especially dangerous in time-sensitive contracts, such as those that involve auctions or token sales.

Real-World Example

An old Ponzi scheme called [GovernMental](http://governmental.github.io/GovernMental/) amassed a considerable quantity of ether. Moreover, it was open to timestamp-based attacks. The last player to join a round (for at least one minute) received payment per the contract terms. A miner who was a player might change the timestamp (to a future time to make it seem like a minute had passed), making it seem like they were the last to join for more than a minute (even though this is not true in reality). 

More detail on this can be found in the [History of Ethereum Security Vulnerabilities Post](https://applicature.com/blog/history-of-ethereum-security-vulnerabilities-hacks-and-their-fixes)
 by Tanya Bahrynovska.

Mitigation:

The following are some mitigation strategies that can be used to address the time manipulation vulnerability in smart contracts:

1. Use Relative Time: Instead of using absolute timestamps, smart contracts can use relative time to determine when certain functions should be executed or funds should be unlocked. This can prevent attackers from manipulating the timestamps to their advantage.
2. Block Verification: Smart contracts can verify the current block number and timestamp before executing certain functions or unlocking funds. This can prevent attackers from exploiting the contract using outdated or manipulated block numbers and timestamps.
3. Third-Party Libraries: Developers can use third-party libraries with secure timestamps and block number verification mechanisms. These libraries can help ensure the integrity and immutability of the blockchain and prevent attackers from exploiting vulnerabilities in smart contracts.

---

Left out:

"Time Manipulation" is a smart contract vulnerability where an attacker exploits the contract by manipulating the timestamps or block numbers to their advantage. For example, they could use this technique to trick a contract into unlocking funds before they are supposed to be available or to access a specific function in the contract at an opportune time. This can be especially dangerous in time-sensitive contracts, such as those that involve auctions or token sales. Time manipulation is one of the common smart contract vulnerabilities that fall under the "Execution" phase of the MITRE framework.