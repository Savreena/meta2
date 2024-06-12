# Project Title

This Solidity application serves as a fundamental framework for controlling token creation and deletion. Managing tokens is similar to managing virtual currency in that you can create new tokens to distribute or
take old tokens out of circulation when they are no longer required. This programme offers a simple approach to play with virtual money by illustrating the basic principles of token issuance and burning. Tokens 
can be burned to effectively remove them from circulation or created in excess to be shared with others.

## Description

A simple token system named "Token," which makes it easier to create and destroy virtual tokens, is presented by this Solidity programme. It monitors each address's balance as well as the overall quantity of 
tokens. The mint function increases the overall supply by enabling the creation of new tokens and allocating them to a certain address. The burn function, on the other hand, eliminates tokens from a specified
address, lowering that address's balance and overall supply. With the help of these straightforward functionalities, users can replicate the issuance and burning of tokens in a safe setting.

## Getting Started

### Installing

1.Rephrased from the original description, the following points describe the Solidity code that was provided:

2.The first section of the contract defines the essential information about the token, such as its name ("DATA"), abbreviation ("DTA"), and initial supply of zero.

3.It uses a mapping structure to keep track of the token balance for every account.

4.A mint function that takes two parameters—an address and a value—is part of the contract. This function adds the designated amount to the address's balance and raises the overall token supply.

5.it has a burn function that lowers the quantity of tokens available. After receiving an address and a value, this function reduces the address's balance and overall supply by the given amount.

6.To guarantee the integrity and fairness of the token system, the burn function includes a check to make sure the address has enough tokens to burn.

### Executing program

# Launching the Software

You can use the online Solidity IDE Remix to run this programme. To get started, take these actions:

1. Go to [Remix](https://remix.ethereum.org/), the website for Remix.

2. Click the "+" icon in the left-hand sidebar of the Remix website to start a new file.

3. Use the  `.sol` extension to save the newly created file, such as `TOKEN.sol.

4. Copy and paste the subsequent code into the file that has just been created:

```

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

contract Token {

    // public variables here to keep information about tokens
    string public tokenName = "DATA";
    string public tokenAbbrv = "DTA";
    uint public totalSupply = 0;

    // mapping variables here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _value)public{
        totalSupply += _value;
        balances[_address] += _value;
    }

    // burn function

     function burn (address _address, uint _value)public{
        if (balances[_address] >= _value) {
        totalSupply -= _value;  //decrease total supply
        balances[_address] -= _value; //Decrease the balance of the address
    }
     }
}
```

Go to the "Solidity Compiler" tab in the sidebar on the left to begin compiling the code. Click "Compile TOKEN.sol" after making sure the compiler version is set to "0.8.18" (or another compatible version).

To deploy the contract, click the "Deploy & Run Transactions" tab in the left-hand sidebar once the code has been compiled. Click "Deploy" after selecting the "TOKEN" contract from the dropdown menu.

You can communicate with the contract once it has been deployed. Select the contract labelled "TOKEN" from the column on the left. By clicking the corresponding buttons, you may verify the token name, token 
abbreviation, and total supply. Click the mint button after entering the address and token value to invoke the mint function. Similar to this, to use the burn function, enter the address and token value and
press the burn button to start it.


## Authors

@Savreena Kaushal


## License

This project `Token` is licensed under the MIT License 
