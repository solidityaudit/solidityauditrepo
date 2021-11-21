---
layout: post
title:  "Anatomy of a Solidity Contract Audit"
categories: [ security audit, tutorial ]
image: https://image.shutterstock.com/z/stock-photo-macro-photo-of-tooth-wheel-mechanism-with-audit-analysis-review-data-report-client-and-asset-741348823.jpg
---



## Why do we need to audit smart contracts?

Smart contracts can have subtle bugs that can be exploited once the contract is deployed. Since it's a smart contract for example an ERC-20 token for example that implements a payments function that can accept and hold ethereum. 

+ ~~strike through~~
+ ==highlight==
+ \*escaped characters\*

# Example of a static analysis audit generated with our toolbox


Pragma version0.8.0 (contract.sol#2) necessitates a version too recent to be trusted. Consider deploying with 0.6.12/0.7.6
solc-0.8.0 is not recommended for deployment
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity

decrement() should be declared external:
	- RolloverExample2.decrement() (contract.sol#7-9)
increment() should be declared external:
	- RolloverExample2.increment() (contract.sol#11-13)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#public-function-that-could-be-declared-external


https://github.com/crytic/slither

# Installing Solidity differnet versions on Mac

QEMU emulator. Can't run fusion on Mac. Emulator required. 

solc-select <version> in pragma.
    
# Different behaviour differnet versions of Soidity. Not backwards compatible

https://hub.docker.com/r/trailofbits/eth-security-toolbox

## What bugs could exist in a smart contract? 

Blockchain - sybl problem solved. Double trasnaction. what would happen if you could double spend?

Classes of bugs

```
.my-link {
    text-decoration: underline;
}
```

## Classes of bugs

![walking]({{ site.baseurl }}/assets/images/8.jpg)

## Reference lists

## What types of audits exist? 

Certik Audit

## What is involved in an audit? 
The quick brown jumped over the lazy.

Another way to insert links in markdown is using reference lists. You might want to use this style of linking to cite reference material in a Wikipedia-style. All of the links are listed at the end of the document, so you can maintain full separation between content and its source or reference.

## Is an audit enough?

Perhaps the best part of Markdown is that you're never limited to just Markdown. You can write HTML directly in the Markdown editor and it will just work as HTML usually does. No limits! Here's a standard YouTube embed code as an example:

<p><iframe style="width:100%;" height="315" src="https://www.youtube.com/embed/Cniqsc9QfDo?rel=0&amp;showinfo=0" frameborder="0" allowfullscreen></iframe></p>
