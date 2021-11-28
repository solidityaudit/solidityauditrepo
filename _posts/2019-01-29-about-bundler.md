---
layout: post
title:  "Part II: Auditing Smart Contracts with Automated Tools"
author: sal
categories: [ Jekyll ]
image: assets/images/2.jpg
---

## Why all these tools for analyzing security in smart contracts?

Ethereum programming best practices are scattered across the web in many blogs, tutorials, videos and papers. Many sources are outdated due to a rapid growth in this area. Automated vulnerability detection tools, which help detect problematic language constructs, are still being actively developed. 

## What kinds of tools are used to audit smart contracts?

We have seen at least two tools that help to find bugs and vulnerabilities in smart contracts. We looked at Trail of Bits's docker image and installed Slither, a static analysis tool written in Python. We also used our own proprietary tool to find a re-enetrancy vulnerability in a smart contract. These tools are just the tip of the iceberg and we are now going to dive a little bit deeper into some other automated tools:

SmartCheck
Mythril
Mythx

## Introducing Smart Check

SmartCheck is an an extensible static analysis tool it converts the solidity smart contract to XML format and then uses xpath expressions to search for vulnerabilities in the code. This type of tool makes it less than ideal for finding more sophisticated attack vectors but is a great tool to be used in combination with Slitherin or when developing your own smart contracts. 

## Myhtril 

Documentation for Mythril project can be found here: https://mythril-classic.readthedocs.io/en/master/mythril.solidity.html

This is a step up from some of the other static analysis tools we've looked at so far. You can set the path for solc to test multiple versions of solidity using --solv <version number>. Please be aware that this uses py-solc and will only work on Linux and macOS. It will check the version of solc in your path, and if this is not what is specified, it will download binaries on Linux or try to compile from source on macOS. This makes it ideal for tesitng many smart contracts at once. 
  
To demo this tool we simply had to pull the docker image and run the following, mounting a volume on our host with the solidity contracts we want to test.

  docker run -v $(pwd):/tmp mythril/myth analyze /tmp/contract.sol

Mythril made it easy to fine tune speed vs coverage with the --execution-timeout option as well as conveniently test on chain contracts with their INFURA support and guess what? They even offer a pro version called Mythx which we definitely wanted to check out. 

Limitations: Mythril is targeted at finding common vulnerabilities, and is not able to discover issues in the business logic of an application, this is one reason why a professional audit with manual review phases are required. 
  
## Mythx
  
In order to use mythx you need an API key as below
  
  $ export MYTHX_ETH_ADDRESS='0x0000000000000000000000000000000000000000'
  $ export MYTHX_PASSWORD='password'

We signed up for one and we were easily able to integrate Mythx into our favorite IDE as well as use it in the Remix editor for a browser based experienced by enabling the Mythx plugin. 
  

# Key Take-aways

* There are many automated tools like Slither, SmartCheck, Mythril and Mythx to help identify vulnerabilities in smart contracts
* Each of these tools have their strengths and weaknesses and detecting errors in business logic should be done by reading code and understanding goals of the smart contract 
* Mythx is a plugin you can use to audit your code to identify common vulnerabilities 

