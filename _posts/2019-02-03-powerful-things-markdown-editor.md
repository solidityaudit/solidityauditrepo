---
layout: post
title:  "Part 1: Layman's Guide to Launching an ERC-20 Fungible Token on PancakeSwap"
author: Jane
categories: [ Open Zeppelin, tutorial, ERC-20, Smart Contracts]
image: https://thumbs.dreamstime.com/z/russia-moscow-businessman-holding-tablet-logo-erc-official-protocol-ethereum-eth-network-standard-creating-tokens-219590148.jpg
tags: [ERC-20, Tokens, Smart Contracts, Pancakeswap]
---
In this 5 part series on auditing smart contracts I want to take a look at an ERC-20 smart contracts. We will use Open Zeppelin to speed up our development process, improve the quality and safety of our smart contract and deploy it to Pancakeswap. 

What is the difference between Ethereum and ERC20?

Unlike Ethereum or Bitcoin which have their own blockchains, ERC-20 run on Ethereum. This is not to diminish the importance of ERC-20 tokens because they run on top of another blockchain. In fact, ERC-20 is a technical standard, it’s one that all smart contracts on the Ethereum blockchain must conform. If you were curious how a project like Chainlink or Tether were created look no further than the ERc-20 standard which allows developers to ceate smart contracts to send, receive and transfer value across the Ethereum network. 

In technical terms, ERC20 contracts keep track of fungible tokens. These are tokens that are exactly equal and make things ideal for smart contracts, staking and more.

#What are some examples of projecs that use ERC-20 smart contracts?

There are many well known projects that use the ERC-20 standard but of course you can create your own too. Here are a few that are top of the list:

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

# How are Smart Contracts developed?

In the next part of our series we will look at tools for developing a simple smart contracts and deploy it to a test network and finally to Pancake swap so it can be traded. As we advance we can talk about auditing our smart contracts for bugs, post-deployment tools for monitoring and security testing as well as more advanced concepts for developres like writing formal tests to help avoid common security issues like re-entrancy, unauthorized access or logical errors. Below is a trivial smart contract we wrote using the browser based IDE (Integrated Development Environment) REMIX: 

![Remix IDE]({{ BASE_PATH }}/assets/images/metamask-remix.png)

# Key Take-aways

* ERC-20 is an open standard for smart contracts running on the Ethereum blockchain
* Safety of smart contract is essential to the success of your project.
* Smart contracts can have many issues like re-entrancy, unauthorized access, overflow/underflow, logical errors or insecure external calls.
* There are many tools for developing smart contracts like Remix editor as well as advanced tools chains to help with monitoring smart contracts once they're deployed. 

Special Thanks to the following resources which helped me out immensely:

- [A Survey of Security Vulnerabilities in Ethereum Smart Contracts by
Noama Fatima Samreen, Manar H. Alalfi](https://arxiv.org/abs/2105.06974)
- [Elliptic Curves Number Theory and Cryptography - by Lawrence Washington](http://www.amazon.com/Elliptic-Curves-Cryptography-Mathematics-Applications/dp/1420071467/)
- [Intro to Cryptography and Data Security - Ruhr University Lectures](https://www.youtube.com/watch?v=HuKT-_PzTIc&list=PLoJC20gNfC2gAB-eg7oaUTheB_JgQY4-q)
- [Flot Javascript Plotting Library](https://github.com/flot/flot)
- [Ruby ECDSA &#124; github.com](https://github.com/DavidEGrayson/ruby_ecdsa)
