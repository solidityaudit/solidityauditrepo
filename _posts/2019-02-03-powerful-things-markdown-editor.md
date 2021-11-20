---
layout: post
title:  "Part 1: Layman's Guide to Launching an ERC-20 Fungible Token"
author: Jane
categories: [ Open Zeppelin, tutorial, ERC-20, Smart Contracts]
image: https://thumbs.dreamstime.com/z/russia-moscow-businessman-holding-tablet-logo-erc-official-protocol-ethereum-eth-network-standard-creating-tokens-219590148.jpg
tags: [ERC-20, Tokens, Smart Contracts]
---
In this 5-part series on auditing smart contracts I want to take an in-depth look at an ERC-20 smart contract. We will use Open Zeppelin to speed up our development process, improve the quality and safety of our smart contract using inheritance before moving onto more advanced topics like security bugs, auditing, post-deploymnent monitoring and writing formal tests. 

What is the difference between Ethereum Blockchain and ERC-20?

ERC-20 token contract keeps track of fungible tokens: any one token is exactly equal to any other token; no tokens have special rights or behavior associated with them. This makes ERC20 tokens useful for things like a medium of exchange currency, voting rights, staking, and of course cryptocurrency. 

Unlike Ethereum or Bitcoin which have their own blockchains, ERC-20 run on Ethereum blockchain. This is not to diminish the importance of ERC-20 because it's not a blockchain, in fact ERC-20 is a technical standard and one one smart contracts on the Ethereum blockchain must conform. If you were curious how a project like Chainlink or Tether were created look no further than the ERC-20 standard which allows developers to ceate smart contracts in a language like Solidity to send, receive and transfer value across the Ethereum network. 

# What are some examples of projecs that use ERC-20 smart contracts?

There are many well known smart contract projects that use the ERC-20 standard but of course you can create your own too. Here are a few that are top of the list:

- Tether (USDT)
- Chainlink (LINK)
- Binance coin (BNB)
- USD coin (USDC)
- Wrapped bitcoin (WBTC)
- Dai (DAI)

# Anatomy of an ERC-20 contract

Let’s take a look at a example ERC-20 contract. For this exercise we can look at Open Zeppelin, an open-source framework for developing secure smart contracts. It’s important to emphasize here that developing a smart contract is only half the battle and before you deploy your contract it needs to be secure and free from logical errors and other bugs that may not be obvious without an audit. One of the ways you can increase the confidence investors have in your smart contract is with an audit which we offer as a service.

Open Zeppelin can help developers by making available high quality modules in Solidity like Safe Math library or entire modules that implement ERC-20 standard functionality and allow contract authors to inherit this high quality code. 

# How are Smart Contracts developed?

In the next part of our series we will look at tools for developing a simple smart contract and deploy a smart contract to a test network. As we advance we can talk about auditing our smart contracts for security vulnerabilities, logical bugs, writing formal tests and using post-deployment monitoring tools to help avoid common security issues like re-entrancy, unauthorized access or logical errors. Below is a trivial smart contract (do not purchase as it is just an example) we wrote using the browser based IDE (Integrated Development Environment) Remix. Many other tools like Hardhat or Truffle exist to help deploy and test smart contracts.

![Remix IDE]({{ BASE_PATH }}/assets/images/metamask-remix.png)

# Key Take-aways

* ERC-20 is an open standard for smart contracts running on the Ethereum blockchain
* Security of smart contract is essential to the success of your project.
* Smart contracts can have many security issues like re-entrancy, unauthorized access, overflow/underflow, logical errors or insecure external calls so need to be audited before they are deployed and traded 
* There are many tools for developing smart contracts like Remix editor, Hardhat or Truffle as well as advanced tools to help with monitoring smart contracts once they're deployed. 

Special Thanks to the following resources which helped me out immensely:

- [A Survey of Security Vulnerabilities in Ethereum Smart Contracts by
Noama Fatima Samreen, Manar H. Alalfi](https://arxiv.org/abs/2105.06974)

