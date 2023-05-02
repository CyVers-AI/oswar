# What is “Command and Control”?

Tags: Command and Control

Malicious actors use various techniques to gain control of validators, smart contracts, or other factors in a network. These techniques are collectively known as command and control (C2). The attacker communicates with an already compromised system to take control of it.

To avoid detection, malicious actors often mimic typical, expected communication patterns. Depending on the network architecture and security measures of the victim, an adversary can establish command and control in different ways and with varying levels of stealth.

C2 is distinct from other subcategories in the framework because it targets an attack's communication and control aspects. While attackers may use other subcategories, such as "Execution" or "Persistence," to achieve their objectives, C2 controls the attack remotely.

Once an attacker gains initial access to a system or network, the next step is establishing a connection between the attacker's command and control infrastructure and the compromised system. This allows the attacker to issue commands, exfiltrate data (which, in this case, is assets), and execute other malicious activities on the compromised system.

However, it's worth noting that the different phases of an attack can often overlap and occur simultaneously. For example, an attacker may use C2 to perform reconnaissance or escalate privileges, which could also be part of the attack's initial "Exploitation" phase.

Overall, the C2 subcategory focuses on an attack's communication and control aspects rather than the attacker's initial entry point or exploitation technique. Defending against C2 attacks requires strong security controls and monitoring for unusual network traffic or communication with suspicious domains or IP addresses.

The C2 subcategory comprises many techniques attackers utilize to gain and maintain control over compromised systems. These techniques may include command and control servers, domain fronting, and peer-to-peer (P2P) communication channels. By employing these methods, attackers can remain undetected by traditional security controls and maintain control over compromised systems.

---

Left out: 

"Command and Control" refers to the technique attackers use to remotely manage and control compromised systems or networks. C2 can be used to issue commands, exfiltrate data, and execute other malicious activities.