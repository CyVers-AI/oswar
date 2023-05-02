# 2. Obfuscation

Category: Money Laundering
Tags: Defense Evasion

## What is "Obfuscation"?

Obfuscation is a technique attackers use to conceal their malicious code or actions. The goal is to make it difficult for defenders to detect and block the attack. The term "obfuscation" comes from the Latin word "obfuscare," which means "to darken" or "to make obscure".

Attackers can use obfuscation techniques to hide their malicious code or actions, making it difficult for defenders to detect and block the attack. For example, code obfuscation techniques can hide malware or malicious smart contracts code in the smart contracts. However, it is not “foolproof” and can be exposed. 

Usually, obfuscation is meant to make the code or data difficult to understand or decipher, thereby making it harder for someone to identify and remove malicious code or contracts. Code compression, renaming variables and functions, and adding dummy code. However, these techniques can be reverse-engineered, and advanced malware detection tools can still identify malicious code even if it is obfuscated. In summary, while obfuscation can make detecting and removing malicious code or contracts harder, it is not a foolproof technique. As such, it is still important to have strong security measures and practices to protect against malware and other malicious activity on blockchains and contracts.

### Examples:

- The attacker can use code obfuscation techniques to make the malicious code harder to understand and detect. This can involve renaming variables, using different encoding techniques, and inserting extraneous code to make it more difficult for an analyst to identify the malicious code. In general, it is done to make the code harder to interpret.
- Storing malicious code off-chain: The attacker can store the malicious code off-chain and only include a small piece of code in the smart contract that interacts with the off-chain code. This can make it harder to detect malicious code because it is not all contained in the smart contract.
- Using a multi-contract architecture: The attacker can use a multi-contract architecture to hide the malicious code in a separate contract that is not easily accessible or visible to outsiders. This can make it harder to detect the malicious code because it is not all contained in one place.

### Mitigation:

To mitigate obfuscation, defenders can use various techniques, including:

- Code analysis tools: Defenders can use tools that analyze code and detect obfuscation techniques. These tools can help identify hidden or obfuscated code and enable defenders to remove it.
- Whitelisting: Defenders can use whitelisting to only allow approved programs to run on a system. This can prevent attackers from running obfuscated code on a system.
- Regular updates: Defenders should regularly update their software and systems to ensure that they have the latest security patches. This can help prevent attackers from exploiting vulnerabilities that may be present in older versions of software or systems.