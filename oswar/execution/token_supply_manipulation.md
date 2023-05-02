# 5.27 Token supply manipulation

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “token supply manipulation”?

Token supply manipulation, also known as "minting" or "inflation", is a vulnerability that can occur in smart contracts that allow for the creation of new tokens beyond the initial supply. This vulnerability can arise if the contract owner or an authorized user can mint new tokens without proper oversight or limitations.

An example of token supply manipulation is if a contract owner can mint new tokens at will, without any restrictions or oversight. This can lead to the dilution of existing token holders' shares and potentially impact the token's value.

An endless mint attack happens when a malicious party or hacker creates excessive tokens within a protocol, raising the supply to an unhealthy level and eroding the token's value. Attackers frequently complete the operation quickly and leave with tokens valued at millions of dollars. Attackers frequently go on to flood the market with all the newly created tokens, driving the price down.
Smart contracts are susceptible to this kind of attack mostly due to code flaws that let hackers take advantage of bugs and weak code areas. 

Example:

Cover Protocol. 

Hackers used shield mining contracts in the Cover Protocol attack to obtain unauthorized crypto rewards from the system. The Cover staking pool's token price fell by 97% due to the hacker's successful use of 40 quintillion tokens on the network. In this instance, the attacker used 1inch to liquidate over 11,700 coins and steal tokens valued at almost $5 million.

```solidity
function _mint(address account, uint256 amount) internal onlyMinter {

        require(account != address(0), "ERC20: mint to the zero address");

        _totalSupply = _totalSupply.add(amount);

        _balances[account] = _balances[account].add(amount);

        emit Transfer(address(0), account, amount;

    }

    function _addMinter(address newMinter) external onlyOwner {

        minters[newMinter] = true; //or minters.push(newMinter);

}
```

A cybersecurity attack that took advantage of a flaw in a Cover Protocol smart contract was known as the Cover Protocol exploited in 2020. Because of the vulnerability, attackers could create COVER tokens indefinitely. A security company rectified the flaw in the Cover Protocol smart contract.

Source: [https://finance.yahoo.com/news/cover-protocol-attack-perpetrated-white-142436248.html?guccounter=1](https://finance.yahoo.com/news/cover-protocol-attack-perpetrated-white-142436248.html?guccounter=1)

Mitigation

To prevent token supply manipulation, it is important to implement proper limitations and oversight mechanisms for the minting function. This can include setting a maximum supply limit, requiring multiple approvals or signatures for minting, or implementing a community-driven governance mechanism to oversee the minting process.

Additionally, it is important to conduct regular audits and security checks of the contract to ensure no vulnerabilities that could allow unauthorized parties to mint new tokens. Any potential vulnerabilities or weaknesses should be identified and addressed promptly to ensure the security and integrity of the contract and its tokens.