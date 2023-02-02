---
title: "TLS - 01 - Objective"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-01-31"
version: 1.0
---


## Objective

Crypto tokens are in the form of smart contract on blockchain. They lack of many anti-fraud measures on fiat currencies or TradeFi securities. Those measures has been deployed because of the centralization in the issuance, governance and exchange for them. With such measures are non-existence in Web3 and DeFi, crypto tokens have relied on users' self-awareness and protocol teams' due diligence for long time. The UX is fragile and vulnerable to trojan, spam and scam.

We hope to address such problem in the TLS (Token Legitimacy Score) project by scoring token by its legitimacy. This score can be determined by various factors from token characteristic, token behavior, characteristic of the entity which issued the token and the behavior of this issuing entity. The higher the score, the more legitimate the token is considered to be. Developers and users can rely on this score to avoid loss and waste of resources.

We hope to score tokens with up-to-date data and calibrated models to achieve timely and accuracy.

## Meaning of legitimacy and illegitimacy

We consider legitimate tokens are going to belong to one of four categories.

1. Value: any token that serves no purpose other than the exchange of value, such as Bitcoin, Monero, or, arguably, Doge.
2. Security: any token which provides access to a potential income stream, such as xxx.
3. Governance: any token that provides voting rights, usually associated with the management of a crypto project, such as xxx.
4. Utility: any token that serves a function in an economic system, such as xxx.

We consider illegitimate tokens are going to belong to one of five categories.

1. Meme: any token that is traded for fun, because it is associated with something cute or popular, such as Doge.
2. Spam: any token designed to entice you to go somewhere, like a website, or do something, such as $USDCBonus.com.
3. Scam: any token used in a scheme to defraud someone of legitimate tokens, such as a token called $AAVE that is not the $AAVE.
4. Rekt: any token was a victim of hacking and attacks, resulting in theft or inflated issuance, leading to loss of value and/or loss of utility, such as MNGO after exploit in Oct 2022.
5. Bankrupt: any token losing its creditworthiness and value due to unfulfilled requirements for collateral and asset backing, such as FTT after FTX’s bankruptcy.

## Usage

1. Avoid loss from transacting the illegitimate tokens
2. Avoid waste in resources to price and exchange the illegitimate tokens.

## Coverage

- We will consider fungible tokens only, i.e. ERC-20 or equivalent token standard/

## Stages

There would be four stages to reach the end goals for a scoring model. Each stage is with a primary goal to achieve.

1. A model that can score the illegitimacy tokens with high accuracy, reduce false negative rate
2. A model that can score the legitimacy tokens with high accuracy and classify them for different purpose, and reduce false positive rate
3. A model that can update timely
4. Calibration the model using historical data and more refinement to the model
