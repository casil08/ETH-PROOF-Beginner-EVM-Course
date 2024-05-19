# Project: Create a Token


## Description

This program is a simple contract written in Solidity, a programming language used for developing smart contracts on the Ethereum blockchain. The contract has a single function that returns the string "Create a Token". This program serves as a simple and straightforward introduction to Solidity programming, and can be used as a stepping stone for more complex projects in the future.

*/
REQUIREMENTS
1. Your contract will have public variables that store the details about your coin (Token Name, Token Abbrv., Total Supply)
2. Your contract will have a mapping of addresses to balances (address => uint)
3. You will have a mint function that takes two parameters: an address and a value. The function then increases the total supply by that number and increases the balance of the “sender” address by that amount
4. Your contract will have a burn function, which works the opposite of the mint function, as it will destroy tokens. It will take an address and value just like the mint functions. It will then deduct the value from the total supply and from the balance of the “sender”.
5. Lastly, your burn function should have conditionals to make sure the balance of "sender" is greater than or equal to the amount that is supposed to be burned.
*/


## Getting Started

### Executing program
To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

Once you are on the Remix website, create a new file by clicking on the "+" icon in the left-hand sidebar. Save the file with a .sol extension (e.g., myToken.sol). Copy and paste the following code into the file:

```
// SPDX-License-Identifier: MIT
pragma solidity 0.8.18;
contract MyToken {

    // public variables here
    string public tokenName = "META";
    string public tokenAbbr = "MTA";
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
        if (balances[_address] >=_value) {
        totalSupply -= _value;
        balances[_address] -= _value; 
        }
    }
}

```

So the last thing to do is to test it. So if we click this symbol, If you don't have auto compile selected, what you'll wanna do is click, compile, and thrn right below that is our deploy interface. We'll go ahead and click deploy. And so if we come down here, we can see our total supply is zero. We got our token name of meta, our abbreviation of MTA looking pretty good. All right, so now let's do something here.

So we need to pass addresses and luckily Remix provides us. Right next to thus is a button to copy it to the clipboard, then we will click this arrow button just to expand this then paste in that address and let's mint say a 1000 tokens to it. Okay, we got a green check mark. 

If we check out total supply, it has increased by a thousand, and if we paste in that same address to our balances, we can see this balance has 8000 thousand tokens. 

So now let's try to burn some tokens. and again paste in that same address and let's burn say half of the supply. 500 

and if we check out total supply. So it has been reduced by 500. If I check our balances, same thing. Its been reduced. 

So now the last thing to check is to make sure that we can't burn more than we have, right? So let's go ahead and put in a 1000 thousand. hmm We'll transact. That just means his function executed successfully.


## Authors

Metacrafter Chris  
[@metacraftersio](https://twitter.com/metacraftersio)


## License

This project is licensed under the MIT License - see the LICENSE.md file for details

