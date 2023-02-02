---
title: "TLS - 03 - Example"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-01-31"
version: 1.0
---

## Examples for the score scale

We divide the score into three ranges, with each range mapping to a kind of tokens

- 10-7: Legitimate
- 6-4: Observation. This range is to park ex-legitimate tokens with deteriorating sub-scores
- 3-0: Illegitimate

For each score, we have a few examples. The tokens and their scores are close to the "ground truth" for model calibration. If there is other opinion, we welcome your feedback.

* 10: Value storing token, e.g. fiat-backed or over-collateralized stablecoin, WETH, WBTC
* 9:  Governance token with voting rights, e.g. CRV, AAVE
* 8:  LP tokens, debt tokens, e.g. aTokens or cTokens
* 7:  Yield-bearing tokens, e.g. y-tokens
* ...:
* 3: Meme tokens, e.g. DOGE, SQUID (after Binance blocks the developer accounts)
* 2: Spam tokens
* 1: Scam tokens
* 0: Rekt/Exploited, e.g. FTT, LunaUST

## Example for TLS result

| Field             | Value                                |
| Internal Token ID | ETH-00001                            |
| Token standard    | ERC-20                               |
| Address           | 0x00... on 1 <br> 0x02... on 37 <br> |
| Inception date    | 02/01/2021                           |
| Project website   | www.token_abc.com                    |
| Token contract    | https://etherscan.io/address/0x00... |
| TLS               | 7.8                                  |
