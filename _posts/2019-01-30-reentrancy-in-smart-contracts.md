---
layout: post
title:  "Re-entrancy Attacks: Auditing a real smart contract"
author: sal
categories: [ Jekyll, tutorial ]
image: assets/images/audit.png
---

## What are re-entrancy attacks?

Re-entrancy attacks inject fallback function calls on the function itself, so the process re-enters the function and then go to fallback function again. This loop goes on endlessly and if the function involves transferring, then it will end up with an empty wallet. Let's take a look at an actaul contract that suffers from the re-entrancy vulnerability and then we will audit it to see if we can catch this bug with our automated tools.

# A vulnerable contract written in Solidity

/* CONTRACT WITH REENTRANCY
 * One of the major dangers of calling external contracts is that they can take over the control flow. 
 * In the reentrancy attack (a.k.a. recursive call attack), a malicious contract calls back into the calling contract before the first invocation of the function is finished. 
 * This may cause the different invocations of the function to interact in undesirable ways.
 * See https://ropsten.etherscan.io/address/0xb03486280c91ab32544aae181f47362dc67c139c#code
 * See https://smartcontractsecurity.github.io/SWC-registry/docs/SWC-107
 */

pragma solidity ^0.4.24;

contract HoneyPot {
    mapping (address => uint) public balances;

    function HoneyPot() payable {
        put();
    }

    function put() payable {
        balances[msg.sender] = msg.value;
    }

    function get() {
        if (!msg.sender.call.value(balances[msg.sender])()) {
            throw;
        }
        balances[msg.sender] = 0;
    }

    function() {
        throw;
    }
}

# Running our proprietary scanner on the following contract 

Re-Entrancy Vulnerability identified: We are at high risk for this see report below:

![rollover]({{ BASE_PATH }}/assets/images/audit.png)


# Additional vulnerabilities we can detect with automated tools

Parity Multisig Bug
Contract A has functions that rely on contract B, contract A cannot guarantee that contract B is in good shape. Happens particularly in Parity contracts.


Transaction-ordering Dependency
The order of transactions getting verified can be manipulated by the miners. If multiple transactions are submitted within the short period of time, it is possible that the later one gets verified before the prior. Thus create problems or conflicts such as a race condition.


Timestamp Dependency
The timestamp is a controllable variable, it is easy to exploit as a factor of the random number. Ex: attackers can send an attack at a specific calculated time, then the randomness of an RNG is eliminated.


Integer Overflow/ Underflow
The unsigned integer should be taken care with boundary with boundary check, because of uint MAX + 1 = uint MIN (and vice versa). This can lead to unexpected outputs or even capital loss if it happens in a transfer function.


Callstack Depth Attack
A function recursively calls itself or another. Imagine the newer call is stack on the prior call. Until a certain depth level, the code can no more be executed.

* This issue was already fixed by Ethereum developers and is no longer able to exploit. But still be aware of potential high gas cost when running recursive calls.

# Key Take-aways

* Re-entrancy is a common vulnerability in smart contracts
* A professional audit can detect re-entrancy and other bugs like timestamp dependency, parity multisig bugs or call stack depth attacks.
* No one static analysis, symbolic execution or dynamic analysis tool identifies all vulenrabilities. 
