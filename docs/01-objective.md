---
title: "TLS - 01 - Objective"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-02-07"
version: 1.0
---


## Objective

Crypto tokens are smart contracts. Because they are decentralized they are not surronded by anti-fraud structures found in traditional finance. Users of centralized financial products enjoy the protection of these, usually invisible, structures. In crypto we rely on users' self-awareness and education, as well developers' care and due diligence. The resulting UX is fragile and vulnerable to trojans, spam and scams.

We hope to partially address this problem with the Token Legitimacy Score (TLS) project. The project will evaluate and score tokens according to criteria that are indicative of legitimacy/illegitimacy. The evaluation will result in a score – a TLS score – being assigned to tokens. 

Scores will be determined by analyzing:

* token characteristics,
* token behavior, 
* token issuer characteristics, and 
* token issuer behavior. 

The higher the TLS score, the more legitimate we determine the token to be. The industry and our thinking are constantly evolving, so the scoring algorithm will as well.

We hope that, over time, developers and users will be able to rely on the TLS score to avoid wasting time, resources, and money.

## Meaning of legitimacy and illegitimacy

Legitimate tokens will belong to one of four categories.

1. Value: any token that serves no purpose other than the exchange of value.
2. Security: any token that represents ownerhip of value.
3. Governance: any token that provides voting rights, usually associated with the management of a crypto project.
4. Utility: any token that serves a function in an economic system.

Illegitimate tokens will belong to one of five categories.

1. Meme: any token that is traded for fun, because it is associated with something cute or popular.
2. Spam: any token designed to entice you to go somewhere, like a website.
3. Scam: any token used in a scheme to defraud someone of legitimate tokens, such as a token called $AAVE that is not the $AAVE.
4. Rekt: any token that has lost its value due to a hack or attack.
5. Bankrupt: any token that has lost its value due to the loss of collateral or the disappearance of a backing entity.

## Usage

There are many reasons to use a TLS score including:

* avoiding losses due to scams,
* not wasting time,
* clean user interfaces, 
* etc.

## Coverage

For the time being we are only covering fungible tokens on EVM chains.

## Stages

We expect this work to go through multiple stages. We currently have four on the drawing board, but there will almost certainly be more. Each stage, as planned, has a single goal. Each model will build on the previous one so the API will only depend on a single model.

1. A model that can score illegitimate tokens with high accuracy: reduce false negatives.
2. A model that can score legitimate tokens with high accuracy and classify them: reduce false positives.
3. A model that can update in response to events: fresher data.
4. A model that makes better use of historical data: increase accuracy.
