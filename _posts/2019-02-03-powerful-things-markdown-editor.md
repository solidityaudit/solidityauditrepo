---
layout: post
title:  "Layman's Guide to Launching an ERC-20 Fungible Token on PancakeSwap"
author: Jane
categories: [ Open Zeppelin, tutorial, ERC-20, Smart Contracts]
image: https://thumbs.dreamstime.com/z/russia-moscow-businessman-holding-tablet-logo-erc-official-protocol-ethereum-eth-network-standard-creating-tokens-219590148.jpg
tags: [ERC-20, Tokens, Smart Contracts, Pancakeswap]
---
In this post I want to take a look at an ERC-20 smart contracts. We will use Open Zeppelin to speed up our development process, improve the quality and safety of our smart contract and deploy it to Pancakeswap. 

What is the difference between Ethereum and ERC20?

Unlike Ethereum or Bitcoin which have their own blockchains, ERC-20 run on Ethereum. This is not to diminish the importance of ERC-20 tokens because they run on top of another blockchain. In fact, ERC-20 is a technical standard, it’s one that all smart contracts on the Ethereum blockchain must conform. If you were curious how a project like Chainlink or Tether were created look no further than the ERc-20 standard which allows developers to ceate smart contracts to send, receive and transfer value across the Ethereum network. 

In technical terms, ERC20 contracts keep track of fungible tokens. These are tokens that are exactly equal and make things ideal for smart contracts, staking and more.

#What are some examples of projecs that use ERC-20 smart contracts?

- Tether (USDT)
- Chainlink (LINK)
- Binance coin (BNB)
- USD coin (USDC)
- Wrapped bitcoin (WBTC)
- Dai (DAI)

#Anatomy of an ERC-20 contract

Let’s take a look at a example ERC20 contract. For this exercise we can look at Open Zeppelin.

Open Zeppelin is an open-source framework for building secure smart contracts. It’s important to emphasize here that programming a smart contract is only half the battle and before you deploy your contract it needs to be secure and bug free. One of the ways we can ensure this and increase the confidence investors have in our smart contract is with an audit which we offer as a service.

Open Zeppelin can help developers achieve this but making available high quality modules in Solidity that implement ERC-20 standard and allow contract authors to inherit this high quality code. In ERC20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and of course cryptocurrency. 

#OpenZeppelin Contracts provides many ERC20-related contracts.

an open source project that is popular in

#Useful resources for learning about smart contracts:

Link to Crypto Zombies: An online school for learning about solidity:

https://cryptozombies.io

# Tools required for Smart Contract Development

![Remix IDE]({{ BASE_PATH }}/assets/images/metamask-remix.png)

# Key Take-aways

* ERC-20 is an open standard for smart contracts running on the Ethereum blockchain
* Safety of smart contract is 
* Given the point, it's impossible to get the multiplier
* You can do addition, subtraction, multiplication, and division with the multiplier (private key); but can only do addition and multiplication with the point (public key)
* Creating a signature requires division (needs the private key), but verifying the signature only needs addition and multiplication (can be done with public key)

Special Thanks to the following resources which helped me out immensely:

- [Understanding Cryptography - by Cristof Paar](http://www.amazon.com/Understanding-Cryptography-Textbook-Students-Practitioners/dp/3642041000)
- [Elliptic Curves Number Theory and Cryptography - by Lawrence Washington](http://www.amazon.com/Elliptic-Curves-Cryptography-Mathematics-Applications/dp/1420071467/)
- [Intro to Cryptography and Data Security - Ruhr University Lectures](https://www.youtube.com/watch?v=HuKT-_PzTIc&list=PLoJC20gNfC2gAB-eg7oaUTheB_JgQY4-q)
- [Flot Javascript Plotting Library](https://github.com/flot/flot)
- [Ruby ECDSA &#124; github.com](https://github.com/DavidEGrayson/ruby_ecdsa)
