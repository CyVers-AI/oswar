# 5.8 Bad Randomness

Category: Logic
Tags: Execution

What is bad randomness?

In Web3, "bad randomness" refers to the lack of or weakness in random number generation in smart contracts, making them vulnerable to attacks. A smart contract's functionality may depend on generating random numbers, for example, in gambling or other games that rely on chance.

If a smart contract's random number generation algorithm is not implemented correctly, an attacker can predict or manipulate it. For example, an attacker could identify patterns in generating random numbers and use this information to manipulate the outcome of a game or other transaction in their favor.

This vulnerability is categorized under the "Execution" phase because it can be exploited during the actual execution of the smart contract. To mitigate this vulnerability, it is important to use secure and unpredictable random number generation methods, such as using multiple sources of randomness or relying on trusted external sources for randomness.

Example

In the 2023 Cyvers Web3 security report, the Wintermute hack was analyzed. One alleged reason for the hack reason of Wintermute was due to the profanity vanity address (private key) generator. 

Its design flaw enabled hackers to predict the outcome through enough computing force. This could be an example of “bad randomness” where hackers could return to the generator and re-compute the answer. It wasn't random enough and followed a pattern that could be “decrypted” through enough computing power.

Mitigation

Preventing "bad randomness" smart contract vulnerability can be challenging, as generating truly random numbers in a deterministic and transparent blockchain environment is difficult. However, there are several techniques and best practices that developers can follow to mitigate this vulnerability:

1. Use External Randomness Sources: Smart contracts can use external randomness sources to generate random numbers, such as the Oraclize service or a trusted decentralized random number generator like Chainlink VRF. These sources provide an additional layer of randomness that is difficult for attackers to predict or manipulate.
2. Avoid Using Block Information: Block information such as the block timestamp or block hash should not be used to generate random numbers, as miners can manipulate them. An attacker who knows the exact block information can generate a predictable outcome and manipulate the contract to their advantage.
3. Pseudorandom Number Generation: If external randomness sources are not available or practical, developers can use pseudorandom number generation techniques. Pseudorandom number generation uses a deterministic algorithm to generate a sequence of numbers that appears random but is repeatable. However, it is important to use a high-quality algorithm and a large enough seed to generate a truly unpredictable sequence.
4. Publicly Verifiable Randomness: Smart contracts should use publicly verifiable randomness techniques that allow anyone to verify the randomness of the generated number. This ensures that the generated number is not biased or manipulated and that the contract operates as intended.
5. Third-Party Auditing: Smart contracts should be audited by third-party security experts to identify and address any vulnerabilities, including bad randomness. This helps ensure that the contract is secure and operates as intended, and can prevent potential loss of funds due to vulnerabilities.