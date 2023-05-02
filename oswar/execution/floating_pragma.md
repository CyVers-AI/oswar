# 5.24 Floating Pragma

Category: Smart Contract Vulnerabilities
Tags: Execution

What is “floating pragma”?

The "floating pragma" is a vulnerability in smart contracts written in the Solidity programming language. Using a floating pragma statement can result in unexpected behavior due to changes in the compiler version.

In Solidity, a pragma statement is used to specify the compiler version that should be used to compile the contract. A floating pragma statement is a pragma statement that uses a caret (^) symbol to allow for automatic updates to the compiler version. For example, the statement "^0.8.0" would allow automatic updates to any version greater than or equal to 0.8.0, but less than 0.9.0.

An example of a floating pragma vulnerability is if a contract uses a floating pragma statement that allows for updates to any version greater than or equal to 0.8.0. If a new compiler version is released that introduces breaking changes to the Solidity language, the contract may be compiled with the new version, resulting in unexpected behavior or even vulnerabilities.

Example

- Unknown

Prevention

To prevent the floating pragma vulnerability, it is recommended to use a fixed pragma statement that specifies a specific compiler version that is known to work with the contract. This can be done by using a pragma statement such as "pragma solidity 0.8.0;" instead of a floating pragma statement. Additionally, contracts should be tested and audited regularly to ensure they remain secure and functional as changes are made to the Solidity language and compiler.

If you leave a floating pragma in your code (*pragma solidity ≥ 0.7.0 < 0.9.0.*), you will not be sure which version has been used to compile your code which means that you might encounter unexpected behaviors.

You should lock the solidity pragma to a specific solidity version so you can be sure of how the contract will behave once deployed.

Source: [https://medium.com/coinmonks/smart-contracts-common-vulnerabilities-solidity-e64c5506b7f4](https://medium.com/coinmonks/smart-contracts-common-vulnerabilities-solidity-e64c5506b7f4)