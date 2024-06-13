# Create a Token

MyToken (MTK) is a simple ERC-20-like token implemented on the Ethereum blockchain. It allows for basic token operations such as minting and burning tokens. This contract serves as a foundational example for creating and managing your own cryptocurrency tokens.

## Description

MyToken is designed to provide a straightforward implementation of a custom token on the Ethereum blockchain. It includes basic functionalities such as:

Minting: Creating new tokens and adding them to an account.

Burning: Destroying tokens and removing them from an account.

This project can be used as a starting point for more complex token systems, including but not limited to utility tokens, governance tokens, or even as a learning tool for understanding blockchain and smart contract development.

## Getting Started


### Installing

To get started with MyToken using Remix, follow these steps:

* Open Remix: Go to Remix IDE = https://remix.ethereum.org/..
* Create a New File: In the Remix file explorer, click the "+" button to create a new file and name it MyToken.sol.
* Copy and paste the following code into the file:

```// SPDX-License-Identifier: MIT
pragma solidity >=0.8.9;

/*
       REQUIREMENTS
    1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
    2. Your contract will have a mapping of addresses to balances (address => uint)
    3. You will have a mint function that takes two parameters: an address and a value. 
       The function then increases the total supply by that number and increases the balance 
       of the “sender” address by that amount
    4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. 
       It will take an address and value just like the mint functions. It will then deduct the value from the total supply 
       and from the balance of the “sender”.
    5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal 
       to the amount that is supposed to be burned.
*/

contract MyToken {

    // Public variables to store token details
    string public tokenName = "MyToken";
    string public tokenAbbrv = "MTK";
    uint public totalSupply = 1000;

    // Mapping from addresses to their balances
    mapping(address => uint) public balances;

    // Mint function to create new tokens
    function mint(address _to, uint _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    // Burn function to destroy tokens
     function burn(address _address, uint _value) public {
        if (balances[_address] >= _value){
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }

}
```
### Compiling the Contract

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.9", and then click on the "Compile MyToken.sol" button.

### Deploying the Contract

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

### Interacting with the Contract

Once deployed, you can interact with the contract using the interface provided in Remix.

1. Minting Tokens

* Expand the Deployed Contract: Click on the deployed MyToken contract to expand its interface.
* Mint Tokens: Locate the mint function. Enter an address (use any address from the provided dropdown) and a value, then click "transact".
* Check Balance: Use the balances mapping to check the balance of the address you minted tokens to.

2. Burning Tokens

* Burn Tokens: Locate the burn function. Enter an address and a value, then click "transact".
* Check Balance: Use the balances mapping to check the balance of the address you burned tokens from.

## Authors

Raj Saini

https://github.com/Raj7665




## License

This project is licensed under the Raj Saini License - see the LICENSE.md file for details
