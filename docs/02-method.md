---
title: "TLS - 01 - Method"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-01-31"
version: 1.0
---

## Score

Although a token's legitimacy is a binary result, TLS score is designed to be from the lowest possible score of 0 to the highest of 10. The higher the score the more likely it is to be legitimate. The reason for using a range of scores is to accommodate a wide variety of tokens. Some tokens are true scams that walks away with your investment funds. Some tokens are just spams that was sent to your wallet randomly. The scores could help differentiate various level of legitimacy. The mapping between score an its meaning will be worked out during the calibration of the model.

## Score composition

The score is a composition from sub-scores. The sub-scores are designed from the below four categories:

- token characteristic
- token behavior
- characteristic of the entity which issued the token
- behavior of this issuing entity

For example, token's name, total supply, circulating supply is for token characteristic. token's distribution pattern is for a token behavior.

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

Some sub-scores can be assigned with some interpretation from raw data, such as project's income.

Some sub-score need to be assigned with expert judgement, such as token's utility in the project, because the utility varies between projects. The expert judgement would be supported and preferable derived from quantitative measures.

Some sub-score need to be normalized with the current market sentiment, such as token's trading volume, so that the sub-score is stable between bear and bull market.

### Producing the TLS from sub-scores

The sub-scores are would have to be normalized before being used to produce the final TLS.

Some sub-scores are more important than others, so they will be given additional weight in the final calculation. Those weights are to be proposed and debated as the sub-scores are defined.

Some sub-scores could have overriding effect to the final score for events like rekted and bankruptcy. The inclusion of "overriding" sub-score is discussed in the adjacent section below.

Once sub-scores are weighted, they are simply averaged.

### Different scoring mechanism for legitimate and illegitimate tokens

Scoring mechanism for legitimate and illegitimate token are not symmetric.

- For legitimate tokens, its legitimacy is found in its designated purpose. Its score is decided by use cases inside or outside the project, as what "DeFi lego" achieves.

- For illegitimate tokens, it can pretend to be a legitimate token in many aspects, however, it will be slashed to be illegitimate when any one of the "overriding" sub-score is breached, such as extraordinary large supply and random distribution pattern.

We will designate some sub-scores to be "overriding" so they can immediately react.

### TLS score calibration

Producing the TLS from the sub-scores is a linear model in general.

We will establish the "ground truth" from know legitimate and illegitimate tokens and use it to calibrate the model for the weights. The weights produced from the "ground truth" will be used to score other tokens.

The model is improved progressively from the four stages described in section 1, minimizing one discrepancy in each stage of progression.

The ground truth could also help to establish guides for score explanation.

## Update frequency

We expect the initial TLS score is able to differentiate between legitimate and illegitimate tokens.

The change of score over time shall reflect primarily how a legitimate token turns to an illegitimate token when its condition deteriorating. Its score could first fall to the medium range and subsequently fall lower, or goes back to a higher score if situation improves. The case of illegitimate tokens turning back to legitimate token is rare.

The data collection and customization to initialize the score will take most of the effort while the subsequent update only performs the data refreshing.
