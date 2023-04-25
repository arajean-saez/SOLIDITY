# SOLIDITY FINAL ASSESSMENT PROJECT

This Solidity is the final project to show off code that creates a basic token contract. This will provide Solidity beginners with a brief introduction to the procedures used to create tokens, burn them, and check the balances. 

## Description

The Ethereum Virtual Machine runs smart contracts created in the programming language Solidity. Making a contract that can be used to create tokens with two variables is necessary for this project. These variables will map addresses to balances and contain public variables that store information about currencies. Then there are two functions: the mint function, which raises the total supply by that amount and raises the address's balance by that same amount, and the burn function, which operates in opposition to the mint function by destroying tokens. However, conditionals are used in burn functions to guarantee that the balance is more than or equal to the amount that should be burned.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., salinas.sol). Copy and paste the following code into the file:

```javascript
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public TokenName = "ALPHA";
    string public TokenAbbrv = "ALP";
    uint public  TotalSupply = 0;

    /// mapping variable here
    mapping(address => uint) public balances;
    
    // mint function
    function mint (address _address, uint _value) public {
       TotalSupply += _value;
       balances[_address] += _value;
    }
    
    // burn function
    function burn (address _address, uint _value) public {
       if (balances[_address] >= _value) {
           
        TotalSupply -= _value;
        balances[_address] -= _value;
       
    }
}
}

To compile the code, click the "Solidity Compiler" tab in the left-hand sidebar. Next, click the "Ara Jean.sol" button, then click compile code and wait for the green check to appear in the "Solidity Compiler" logo. After that, using the "Deploy & Run Transactions" tab in the left-hand sidebar, you can deploy the contract after the code has been compiled. From the drop-down menu, choose the "Ara Jean.sol" contract, and then press the "Deploy" button. When the contract is ready for use, you can interact with it by expanding the Deployed Contracts area below the address. Simply clicking the arrow button on the left side of your deployed contract will expand it. You can now interact with the contract you generated. To set up the changes, simply enter the necessary information, such as the address (just copy the account address), the token's value, and the number of tokens you wish to mint, burn, and then transact. Just select "balances" to check it.

## Authors

Saez, Ara Jean A.

## License

This project is licensed under the MIT License - see the LICENSE.md file for details
