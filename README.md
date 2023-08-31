# MyToken Solidity Contract

This Solidity contract demonstrates the basic functionality of a simple token contract called "MyToken." It includes features for minting and burning tokens, and provides an example of using a mapping to track token balances. This README will guide you through compiling and deploying the contract using Remix, an online Solidity IDE.

## Description

The "MyToken" contract is a simple token contract written in Solidity. It showcases the implementation of token minting and burning functionalities. The contract uses a mapping to keep track of token balances for different addresses. This example serves as an introduction to basic token contracts on the Ethereum blockchain.

## Getting Started

### Prerequisites

- Access to an Ethereum wallet and Remix Solidity IDE (https://remix.ethereum.org/).

### Deployment

1. Open Remix in your web browser.

2. Create a new file named `MyToken.sol`.

3. Copy and paste the following Solidity code into the file:

solidity
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // Public variables
    string public tokenName = "METAINDIGO";
    string public tokenAbbrev = "MIDG";
    uint public totalSupply = 1000000;

    // Mapping to store balances
    mapping (address => uint) public balances;

    // Mint function
    function mint(address _to, uint _value) public {
        // In real use cases, you MUST use the `require` function here
        balances[_to] += _value;
        totalSupply += _value;
    }

    // Burn function
    function burn(address _from, uint _value) public {
        if (balances[_from] >= _value) {
            totalSupply -= _value;
            balances[_from] -= _value;
        }
    }
}


4. Compile the contract by clicking on the "Solidity Compiler" tab, ensuring the compiler version is set to `0.8.18`, and then clicking on the "Compile MyToken.sol" button.

5. Deploy the contract by clicking on the "Deploy & Run Transactions" tab. Select the `MyToken` contract from the dropdown menu, and then click on the "Deploy" button.

6. Once the contract is deployed, you can interact with it:
   - To mint tokens, click on the `mint` function under the deployed contract, provide the recipient address (`_to`) and the amount (`_value`), and then click "transact."
   - To burn tokens, click on the `burn` function, provide the sender address (`_from`) and the amount (`_value`), and then click "transact."

Remember that this example lacks certain security features for simplicity. In real-world scenarios, additional checks and validations are necessary.

## Authors

Ifeanyi Febian Ezeanekwe

## License

This project is licensed under the MIT License - see the LICENSE.md file for details.
