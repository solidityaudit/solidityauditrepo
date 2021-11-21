---
layout: post
title:  "Anatomy of a Solidity Contract Audit"
categories: [ security audit, tutorial ]
image: https://image.shutterstock.com/z/stock-photo-macro-photo-of-tooth-wheel-mechanism-with-audit-analysis-review-data-report-client-and-asset-741348823.jpg
---



## Why do we need to audit smart contracts?

Smart contracts can have subtle bugs, errors in business logic and vulnerabilities that can be exploited once the contract is deployed. Unlike other software where if a bug is found in a production environment, a hotfix can be deployed immediately, once your contract is on the blockchain it exists on teh blockchain forever. This is by design because it ensures the rules of the contract are followed and cannot be changed arbitrarily by a third party or even by the owner of the contract, but it creates a technical challenge. The best way to address this technical challenge is to audit your smart contracts prior to deploying them so you can identify and fix any security vulneriabilities. In fact, up to 75% of smart contracts do not have audits or are using fake audits so a good investor should always look for an audit and do their own research. 

# Integer underflow and Integer Overflow in Solidity

In previous versions of Solidity (prior Solidity 0.8.x) an integer would automatically roll-over to a lower or higher number. If you would decrement 0 by 1 (0-1) on an unsigned integer, the result would not be -1, or an error, the result would simple be: MAX(uint). In versions 0.8.x of the solidity compiler, this problem is addressed as you need an unchecked keyword if you want integers to rollover. In other words, decrementing an integer 

In our previous example worked with uint256, but bear with me for a moment. Uint8 is going from 0 to 2^8 - 1. In other words: uint8 ranges from 0 to 255. If you increment 255 it will automatically be 0, if you decrement 0, it will become 255. No warnings, no errors. For example, this can become problematic, if you store a token-balance in a variable and decrement it without checking, or worse, exposed a public method that can decrement your balance indefinitely perhaps unintentionally via a re-entrancy vulnerability, eventually the balance would wrap around to MAX(uint) and your contract would have a major security flaw. 

# Static Analysis to the Rescue

Let's take a look at a contract that has this flaw. Note that the version of solidity is important, this is given in the pragma after the SPDX-License-Identifier. Because we're using 0.8.0 this contract will not rollover but if we changed version to 0.7.0 and deployed this to main net, it would be extremely insecure. In addition there are several other issues with this contract that we can pick up via a tool like Slither. Let's install solidity and run Slither on the following contract:

// SPDX-License-Identifier: MIT
pragma solidity 0.8.0;

contract RolloverExample {
    uint8 public myUint8;

    function decrement() public {
        myUint8--;
    }

    function increment() public {
        myUint8++;
    }
}

# Installing Solidity 

The first step is to install the correct version of solidity compiler, I'd recommend using docker containers for this (I'm on a MAC book air with an Apple Silicon so I had some issues running containers built for intel or amd 64 architectures but you can also use emulation on QEMU if you're so inclined). 

You can also download slither at: 

# What are static analysis tools?

![rollover]({{ BASE_PATH }}/assets/images/rollover.png)

If you're a developer, it's good practice to run linters or static analysis tools on your code as part of your development lifecycle. Although a static analysis is not the same thing as a full fledged security audit (which should involve a human reading your code), a static analyzer like Slither can help you to become a better developer and identify major classes of bugs and vulneriabilities. The first step would be to install 

# Static Analysis Results

Pragma version0.8.0 (contract.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
solc-0.8.0 is not recommended for deployment
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity

decrement() should be declared external:
	- RolloverExample2.decrement() (contract.sol#7-9)
increment() should be declared external:
	- RolloverExample2.increment() (contract.sol#11-13)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#public-function-that-could-be-declared-external

# Interpretting results 

From the simple static analysis we can gather that we should probably use an older version of Solidity, one that is perhaps more stable like 0.7.6. This might answer a question I had earlier about why you often seen older versions of solidity in the wild, it' because they're battle tested and thus more trustworthy. 

Another problem we see is we forgot to add the eternal declaration to our decrement and increment functions. This saves us some gas because these functions are never called by our contract. 

## Reference lists

## What types of audits exist? 
