# 5.5 Access Control Issues

Category: Smart Contract Vulnerabilities
Tags: Execution

What is Access control?

Access control issues refer to a type of security vulnerability that occurs when inadequate controls or restrictions exist on who can access and modify certain resources or data within a system. This vulnerability can occur in various system areas, including user accounts, databases, APIs, and smart contracts.

Example 

In the context of smart contracts, access control issues can arise when there need to be more restrictions on who can execute certain functions or modify the state of the contract. For example, suppose a smart contract needs proper access controls. In that case, a malicious actor may be able to manipulate the contract's data or execute unauthorized functions, leading to various types of attacks, such as theft of funds or unauthorized data access.

Access control issues can also arise in decentralized applications (dApps) that rely on smart contracts. In these cases, the issue may be related to the dApp's user interface, which could allow malicious actors to bypass certain access controls or execute unauthorized functions within the smart contract.

Mitigation

To prevent access control issues, it is essential to implement proper authentication and authorization mechanisms that limit access to sensitive resources and ensure that only authorized users can execute certain functions or modify certain data. This includes implementing multi-factor authentication, role-based access control, and secure coding practices when developing smart contracts and dApps.

Similar to “15.1 validator privileges,” - Inadequate access control smart contracts give hackers access through the lack of restrictions in updating the smart contract state.