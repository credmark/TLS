---
title: "TLS - 04 - Example"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-02-07"
version: 1.0
---

## Examples for the score scale

For now we are dividing scores into three ranges:

- 10-7: Legitimate
- 6-4: Indeterminate (e.g., previously legitimate tokens with deteriorating sub-scores)
- 3-0: Illegitimate

For each score, we have a few examples. The tokens and their scores are close to the "ground truth" for model calibration. This is an area of research and we welcome feedback.

* 10: Value storing token, e.g. fiat-backed or over-collateralized stablecoin, WETH, WBTC
* 9:  Governance tokens with voting rights, e.g. CRV, AAVE
* 8:  LP tokens, debt tokens, e.g. aTokens or cTokens
* 7:  Yield-bearing tokens, e.g. y-tokens
* ...:
* 3: Meme tokens, e.g. DOGE, SQUID (after Binance blocked the developer accounts)
* 2: Spam tokens
* 1: Scam tokens
* 0: Rekt/Exploited, e.g. FTT, LunaUST

## Example TLS result fields

| Field | Value |
| --- | --- | 
| Internal Token ID | ETH-00001 |
| Token standard | ERC-20 |
| Address | 0x00... | 
| Inception date | 2021/01/02 |
| Project website | www.token_abc.com |
| Token contract | https://etherscan.io/address/0x00... |
| TLS | 7.8 |

