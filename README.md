# Create a token

This is a basic solidity smart contract code that creates and deletes tokens. We can create tokens using the mint function, and delete tokens using the burn function.

## Description

The smart contract's code includes three public variables: tokenname, tokenAbbrv, and totalSupply. There are two functions called mint and burn that allow users to generate and delete tokens based on the value parameter specified. When using these functions, mint creates new tokens while burn removes them.

### Executing program

To execute the contract, you can simply copy and paste the code into RemixIDE. From there, you can easily compile and deploy the contract with just a few clicks. It's that simple!

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

contract MyToken {

    // public variables here
    string public tokenname = "ABHISHEK"; 
    string public tokenAbbrv = "ABI"; 
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

## License

This project is licensed under the MIT License
