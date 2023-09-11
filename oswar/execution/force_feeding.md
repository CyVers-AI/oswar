# Force-feeding Attacks

Category: Smart Contract Vulnerabilities Tags: Execution

## What are Force-feeding Attacks?
Smart contracts can be forced to recieve ETH without executing any code blocks. Developers cannot prevent contracts from accepting ETH.
Function logic that is dependent upon an address' balance is now subject to being manipulated by a force-feeding attack.

## Example
```
contract Attacker {
  function receive_ETH(address victim) payable {
    selfdestruct(victim);
    }
}
```

## Mitigations
- Implement checks to handle use-case for logic functionality relying on balances
- Stir away from relying on address or EOA balance in SC(smart contact) logic 
- Don't assume a SC can block ETH being sent to it. SCs can send value, no value, and data.

Sources:
- [9 smart contract vulnerabilities and how to mitigate them](https://www.techtarget.com/searchsecurity/tip/Smart-contract-vulnerabilities-and-how-to-mitigate-them)
- [Attack Playbook by Rektify AI](https://github.com/RektifyAI/attack-playbook)
