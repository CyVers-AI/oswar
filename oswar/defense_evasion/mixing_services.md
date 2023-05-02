# 1. Mixing services

Category: Money Laundering
Tags: Defense Evasion

**What are mixing services?**

Mixer services are tools used by attackers, such as Tornado Cash, to conceal their transactions and make it difficult to trace their actions on the blockchain. This can pose a challenge for defenders in tracking and blocking the attack. Mixer services are a common example of defense evasion techniques used in the Web3 world to hide the flow of cryptocurrency transactions. They are also known as tumblers or coin mixers, designed to help users obscure the origins and destinations of their transactions.

Mixer services work by receiving cryptocurrency from a user, mixing it with other coins in their pool, and returning it to the user in a way that makes it difficult to trace the original transaction.

**Example**

One popular mixer service in the Web3 world is Tornado Cash. It provides high anonymity to users who want to protect their transactions. Tornado Cash is an Ethereum-based mixing service that uses smart contracts to break the transaction link between the original and new addresses. The smart contracts hold a pool of ETH, which users can deposit into using their wallets. Once the funds are deposited, the smart contracts mix them with other deposits and return them to the user's new address in the form of a new ETH amount with a different history. Before an attack, Tornado Cash is used by Web3 users who want to hide their cryptocurrency transactions from being tracked or traced by other users or even government authorities. Using Tornado Cash, these users can protect their privacy and hide their financial activities from others. After an attack, hackers or malicious actors can use Tornado Cash to obscure their financial transactions and prevent investigators from tracking their movements.

Attackers can use Tornado Cash or similar mixing services to mix stolen funds with other coins, making them difficult or impossible to trace. This makes it harder for law enforcement or investigators to identify and recover the stolen funds. However, it should be noted that the use of mixer services is not illegal, and many legitimate users may use them for privacy reasons. Only when the services are used for illegal activities do they become problematic.

**Mitigation:**

As of 2022, some nodes have started to block processing transactions of wallets blacklisted by OFAC. Wallets that have interacted with the mixer can be blacklisted, preventing them from using the services in the future. However, currently, it is almost impossible to prevent the use of mixing services as they are open-source software.