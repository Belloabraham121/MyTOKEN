# My Token

This is a Solidiy program that demonstrates how i created a simple token. 

## Description

This Solidity contract, named MyToken, is designed to implement a basic cryptocurrency token with functionalities for minting (creating) and burning (destroying) tokens. Here's a brief description of the code for a GitHub repository:

## Getting Started

## Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

## Explaining the code
1. Token Details: Public variables TokenName, tokenAbbrv, and totalSupply store essential details about the cryptocurrency token, including its name, abbreviation, and total supply.
2. Address Balances: The contract maintains a mapping named balances that associates addresses with their respective token balances.
3. Mint Function: The mint function allows the creation of new tokens by increasing the total supply and the balance of a specified address. It takes two parameters: _address, representing the address to which the tokens will be minted, and _value, indicating the number of tokens to mint.
4.Burn Function: The burn function enables the destruction of tokens by decreasing the total supply and the balance of a specified address. It takes two parameters: _address, representing the address from which tokens will be burned, and _value, indicating the number of tokens to burn. Before performing the burn operation, it checks whether the balance of the given address is sufficient to cover the burn amount.

```javascript
pragma solidity 0.8.18;

contract MyToken {    

    // public variables here
    string public TokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;
contract MyToken {

    // public variables here
    string public TokenName = "META";
    string public tokenAbbrv = "MTA";
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function
     function burn (address _address, uint _value) public {
        if (balances[_address] >= _value) {
            totalSupply -= _value;
            balances[_address] -= _value;
        }
    }
}
```
## Purpose
This code serves as a foundational smart contract for creating and managing a custom cryptocurrency token on the Ethereum blockchain. It can be utilized as a starting point for various decentralized applications (DApps), token issuance platforms, or blockchain-based projects that require custom token functionality.

To compile the code, click on the "Solidity Compiler" tab in the left-hand sidebar. Make sure the "Compiler" option is set to "0.8.4" (or another compatible version), and then click on the "Compile HelloWorld.sol" button.

Once the code is compiled, you can deploy the contract by clicking on the "Deploy & Run Transactions" tab in the left-hand sidebar. Select the "HelloWorld" contract from the dropdown menu, and then click on the "Deploy" button.

Once the contract is deployed, you can interact with it by calling the sayHello function. Click on the "HelloWorld" contract in the left-hand sidebar, and then click on the "sayHello" function. Finally, click on the "transact" button to execute the function and retrieve the "Hello World!" message.


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
