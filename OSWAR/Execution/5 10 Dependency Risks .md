# 5.10 Dependency Risks

Category: Smart Contract Vulnerabilities
Tags: Execution

What are “Dependency Risks”?

In the context of smart contracts, dependency risk refers to the potential vulnerabilities that can be introduced into the smart contract code due to external dependencies such as libraries or APIs.

Smart contracts often rely on external dependencies to perform certain functions or access external resources such as external data feeds or other smart contracts. However, if these external dependencies are not properly secured or validated, they can introduce vulnerabilities in the smart contract code. For example, an attacker could exploit a vulnerability in an external library used by a smart contract to gain unauthorized access to the smart contract's funds or execute malicious code.

Examples

1. Malicious Dependencies: This refers to using a malicious dependency by a smart contract. It can happen when a developer unknowingly uses a third-party library that contains malicious code, which can then be used to exploit the smart contract.
2. Versioning Issues: Versioning issues arise when a smart contract relies on a specific dependency version, which becomes deprecated or is no longer supported. If the developer doesn't update the dependency, it can lead to potential security vulnerabilities.
3. Conflicting Dependencies: Sometimes, different dependencies can have conflicting versions of the same library, which can cause issues in the smart contract. If the smart contract relies on these dependencies, it can lead to unexpected behavior or security vulnerabilities.
4. Package Management Issues: Smart contracts can have package management issues if they use a package manager that is not secure or is susceptible to attacks. Attackers can then inject malicious code into the package manager, which can then be used to exploit the smart contract.
5. Abandoned Dependencies: Sometimes, dependencies can become abandoned by the developer, meaning they are no longer maintained or updated. If the smart contract relies on these dependencies, it can lead to potential security vulnerabilities, as any issues or bugs in the dependency will not be addressed.

**Mitigation:**

To mitigate dependency risk, smart contract developers should carefully vet and validate any external dependencies used in their code. They should also consider using secure coding practices such as input validation and defensive programming techniques to prevent potential attacks. Additionally, developers should regularly monitor and update their dependencies to promptly address any vulnerabilities or security issues.