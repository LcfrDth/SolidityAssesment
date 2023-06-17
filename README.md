# Getting Started with Solidity Assesment 

This is an illustration of a straightforward cryptocurrency contract written in the Solidity programming language. It enables the creation and destruction of tokens, as well as the real-time monitoring of their circulation and value. All the terms and conditions of the contract are outlined in this document.

## Description

The Coin Contract is a Solidity smart contract that facilitates the minting and burning of tokens. It maintains a record of token ownership and tracks the circulation of tokens. The contract includes public variables that store token-specific details such as the Token Name, Token Abbreviation, and Total Supply. Token ownership is managed through a mapping of addresses to balances.

The contract incorporates a mint function that increases the token supply and adds the same amount to the balance of the "sender" address. Conversely, the burn function reduces the overall token supply and subtracts tokens from the balance of the "sender" address. The burn function includes conditional statements to ensure that the "sender" address has a positive balance greater than or equal to the amount being burned.

### Setting Up

Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension.

```javascript

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

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

    // public variables here
    string public tokenName = "DAEMON";
    string public tokenAbrv = "DMN";
    uint public totalSupply = 0;

    // mapping variable here
    mapping (address => uint) public balances;

    // mint function
    function mint (address _address, uint _value) public {
        totalSupply += _value;
        balances [_address] += _value;
    }

    // burn function
      function burn (address _address, uint _value) public {
        if (balances [_address] >= _value){
            totalSupply -= _value;
            balances [_address] -= _value;
        }
    }
}

```


1. Get the code from the Solidity file or copy the code above.
2. Use a Solidity compiler or development environment of your choosing to compile the Solidity code.
3. Use a tool which is Remix to release the built contract on the Ethereum network of your choosing.

After deploying the contract, users can utilize the provided methods to access and engage with it. To create tokens, the mint function can be used by specifying the recipient's address and the desired value (number of tokens). On the other hand, tokens can be removed by employing the burn function, which requires entering the token owner's address and the value of tokens to be eradicated. This function will deduct the specified amount from the total supply and reduce the balance of the sender's address by the same quantity.

## Help

If you have any problems or queries when working with Solidity, see the relevant documentation for your compiler or development environment. Support from online Solidity developer groups or forums is also available.

## Authors

Mark Arceo - Mapua University
