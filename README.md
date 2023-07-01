# Hello World

A contract that mints and burns tokens and checks the current value of the balance of the account (address).

## Description

This program mints or creates new tokens to the address and then you can burn the tokens that was created or added to the address.
There is also a condition within the program that prevents the users to burn more than the amount of the current balances.

## Getting Started

### Executing program

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;

contract MyToken {

    // public variables here
    string public tokenName = "CaelestisMyojo"; // change variable name
    string public tokenAbbrv = "GDDSS"; //change variable name
    uint public totalSupply = 0;

    // mapping variable here
    mapping(address => uint) public balances;

    // mint function
    function mint (address _address, uint _values) public {
        totalSupply += _values;
        balances [_address] += _values;
    }

    // burn function
    function burn (address _address, uint _values) public {
        if (balances [_address] >= _values) {
            totalSupply -= _values; 
            balances [_address] -= _values; 
        }
        
    }
}


## Authors

Torayno, Joshua C. also known as Goddess Luxanna


## License

This project is licensed under the MIT License - see the LICENSE.md file for details
