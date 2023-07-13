# juhiToken Contract

This contract implements a basic ERC-20 token called "SOLIDITY" with the token abbreviation "SOL". It provides functionalities to mint and burn tokens.

## Contract Details

- Token Name: SOLIDITY
- Token Abbreviation: SOL
- Total Supply: 0

## Public Variables

The contract has the following public variables:

- `tokenName`: A string variable representing the name of the token.
- `tokenAbbrv`: A string variable representing the abbreviation of the token.
- `totalSupply`: An unsigned integer variable representing the total supply of the token.

## Mapping

The contract uses a mapping called `balances` to store the token balances of addresses. It maps addresses to their respective token balances.

## Functions

### `mint(address _address, uint _value)`

The `mint` function allows minting new tokens. It takes two parameters: `_address`, which represents the address to receive the minted tokens, and `_value`, which specifies the amount of tokens to mint. The function increases the total supply by the `_value` and increases the balance of the `_address` by the same amount.

### `burn(address _address, uint _value)`

The `burn` function allows burning existing tokens. It takes two parameters: `_address`, which represents the address to burn tokens from, and `_value`, which specifies the amount of tokens to burn. The function first checks if the balance of the `_address` is greater than or equal to `_value`. If it is, the function deducts the `_value` from the total supply and decreases the balance of the `_address` by the same amount.

Note: The burn function includes a conditional check to ensure that the balance of the `_address` is sufficient to burn the requested amount.
# ETH-PROOF-Beginner-
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

contract pranavToken {

    // public variables here
    string public tokenName = "SOLIDITY";
    string public tokenAbbrv = "SOL";
    uint public totalSupply = 0;
    // mapping variable here
    mapping(address => uint) public balances;
    // mint function
    function mint (address _address, uint _value) public{
        totalSupply += _value;
        balances[_address] += _value;
    }
    // burn function
    function burn (address _address, uint _value) public{
        if (balances[_address] >= _value){
        totalSupply -= _value;
        balances[_address] -= _value;
        }
    }    
}
