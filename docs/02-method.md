---
title: "TLS - 02 - Method"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-02-07"
version: 1.0
---

## Score

Just as credit scores aren't binary, TLSes aren't binary. A TLS is a value in the range of 0-10. The higher the score the more likely it is to be legitimate. We use a range because the idea of "legitimacy" is a continuum. A token designed to steal your funds is truly illegitimate, but an airdropped token designed to make you visit a website is arguably somewhat legitimate. 

The mapping between score rangees and their meaning, i.e., something more readily understandable to humans, will be worked out during the calibration of the model.

## Score composition

The score is a composition from sub-scores. We currently expect all sub-scores to belong to one of four categories:

- token characteristics
- token behavior
- token issuing entity characteristic
- token issuing entity behavior

For example, a token's name, total supply, circulating supply are token characteristics. A token's distribution pattern is token behavior.

Sub-scores could be simple and binary, or complex and non-binary.

### Token characteristic sub-score example

For a token's total supply, we could say that a supply (a) between 1 and 10,000 or (b) greater than 10 billion is “abnormal”. We could assign a sub-score of 0 to indicate an “abnormal” supply and 1 to indicate a “normal” supply.

Or we could be more subtle and define degrees of “normalcy”.

### Token behavior sub-score example

We might have a sub-score for token distribution patterns. Excessive concentration or excessive scattering might produce negative sub-scores while more standard distribution patterns might produce positive sub-scores.

### Entity characteristic sub-score example

An DAO whose founders and contributors are all anonymous might produce a poor sub-score, for example, whilst a regulated entity like Coinbase might produce a more positive sub-score.

### Entity behavior sub-score example

An entity that sold $25M of tokens but hasn’t updated its website for two years might generate a negative sub-score, while an entity that consistently delivers on its roadmap might produce a more positive sub-score.

## Score generation

### Sub-score generation

Some sub-scores can be derived purely from raw chaing data, such as a project's income.

Some sub-score may need input from humans. This project may not do this directly but could, indirectly, include human input by consulting data produced by CoinMarketCap, for example. Some of that data is produced with human intervention.

Some sub-score will need to be normalized against the current market. A sub-score that analyzed trading volume, for example, should be designed to be stable irrispective of macro market conditions.

### Producing the TLS from sub-scores

All sub-scores will need to be normalized before being used to produce the final TLS.

Some sub-scores are more important than others, so they will be given additional weight in the final calculation. Those weights are to be proposed and debated as the sub-scores are defined.

Some sub-scores could have overriding effect on the final score for events like rekted and bankruptcy. The inclusion of "overriding" sub-score is discussed in the adjacent section below.

Once sub-scores are weighted, they are simply averaged.

### Different scoring mechanism for legitimate and illegitimate tokens

Scoring mechanism for legitimate and illegitimate token are not symmetric.

- For legitimate tokens, its legitimacy is found in the token's designated purpose. The socring will have to consider use cases within the project context and outside of that context, for example, the protocol's inclusing in a recognized "DeFi lego" stack.

- For illegitimate tokens, it can pretend to be a legitimate token in many aspects, however, it will be slashed to be illegitimate when any one of the "overriding" sub-score is breached, such as extraordinary large supply and random distribution pattern.

We will designate some sub-scores to be "overriding" so they can immediately react.

### TLS calibration

Producing the TLS from the sub-scores is a linear model in general.

We will establish the "ground truth" from know legitimate and illegitimate tokens and use it to calibrate the model for the weights. The weights produced from the "ground truth" will be used to score other tokens.

The model is improved progressively from the four stages described in section 1, minimizing one discrepancy in each stage of progression.

The ground truth could also help to establish guides for score explanation.

## Update frequency

We expect the initial TLS is able to differentiate between legitimate and illegitimate tokens.

The change of score over time shall reflect primarily how a legitimate token becomes illegitimate when its condition deteriorating. Its score could first fall to the medium range and subsequently fall lower, or goes back to a higher range if its situation improves. The case of illegitimate tokens becoming more legitimate is likely rare.

The data collection and customization to initialize the score will take most of the effort while subsequent updates only require data refreshing.
