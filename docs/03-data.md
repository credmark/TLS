---
title: "TLS - 03 - Data"
author: "paul@credmark.com, kunlun@credmark.com"
date: "2023-02-07"
version: 1.0
---

## Data sources

The data source is broadly divided into off-chain and on-chain data.

### Off-chain data

The sources are

- Centralized exchanges
- Token information websites
    + e.g., CoinMarketCap or CoinGecko
- Protocol websites

The data to be collected is

1. Token meta data
2. Listing exchanges
3. Historical price and volume
4. Circulating supply amount
5. Contract audit status

We currently do not include social media because the signal-to-noise ratio is so low.

### On-chain data

- Chain explorers, e.g. Etherscan, Polyscan
    + To retrieve the ABI and source code of the smart contract.
- Dune tables
- The Graph Sub-graphs
- Credmark models

Currently, token information can be retrieved from Credmark using either:

1. The [Token API](https://gateway.credmark.com/api/#/Token%20API), or
2. models accessible via the [DeFi API](https://gateway.credmark.com/api/#/DeFi%20API).

Relevant models include:

- Token price: model `price.dex-db`
- All trading pairs of a Token: model `pools.token-dex-db`
- Trading volume of a DEX pool: model `pools.dex-db`
- total supply: model `token.total-supply`
- holders: model `token.holders`

More models will be created to retrieve data as needed.

## Data for token behavior

The behavioral data of tokens and token holders is a large variable in the TLS. Token behavior is recorded on-chain, and therefore easy to track. The behavior of token issuers will require research conducted by humans.

Token behavioral data can be divided into two types

- price-related, and 
- non-price-related.

Price-related data has attracted much attention in DeFi and has been well researched. For the TLS, a surging price and trading volume does not necessarily make a token more legitimate, but sharp price and volume drops are a clearer indicator of illegitimacy.

The TLS is expected to be more sensitive to the downside of price-related data. Positive data will need to be elevated for longer to positively contribute to the score.

Price-related data has its limitation. For tokens with a small trading volume, such as LP tokens and staked tokens, we would need to look beyond the exchanges and look at factors such as mint/redeem patterns, governance votes, etc.

Crypto tokens have many use cases. The TLS will have to take this into account.

### A generic on-chain transaction scoring model

As all ERC-20 tokens emit the Transfer event, we would like to develop a generic usage scoring model to process this transaction data. We expect to find patterns akin to these:

- Legitimate token:
    + Lots of transaction flows
    + Transaction volume that follow Benford's law (our hypothesis to test)
    + Growth of user base (new addresses)
    + Stable trading volume
- Illegitimate tokens:
    + Surge in short-period of time
    + Only one-way transfers, no further usage.

This model can be built entirely with on-chain data.

#### Test drive of the idea

We did an simple test drive of this idea with Credmark's on-chain dataset.

We collected the transfer data for the following tokens. Two of them are illegitimate tokens.

- legitimate tokens: 'CRV', 'cvxCRV', 'UNI', 'LINK', 'WETH', 'WBTC', and
- illegitimate tokens: 0x208A9C9D8E1d33a4f5b371Bf1864AA125379Ba1B, 0x471c3A7f132bc94938516CB2Bf6f02C7521D2797.

For legitimate tokens, we found associated transactions every day. We saw many transactions for small amounts and a few transactions for large amounts. The distribution is relatively standard across tokens.

For illegitimate tokens, we only found transactions over short periods of time.

1. 0x208A... was active for 1 day 17.8 hours during block range (15680216, 15667775).
2. 0x471c... was active for 4 day 5.5 hours during block range (14884786, 14858859).

For token 0x208A9.., the scammer is sophisticated. First, token transfers mimick the pattern found for legitimate tokens. Second, the token is named  "Asense.fi Yield Finance". There is a DeFi project with a similar name, called Sense Finance (https://sense.finance/). Sense Finance planned to issue a "Yield Token" as a DeFi product, but hadn't when the airdrop of this token was made. We weren't able to determine the legitimacy of token by analyzing its transfer patterns, but we did notice that its source code was never submitted to Etherscan. Further investigation confirmed that the token was not issued by Sense.

For token 0x471c3.., the analysis was much simpler. Every airdrop transaction was for 250,457 tokens!

![](distribution-token-transfer.png)

As you can see, the distribution of transfer amounts is not enough to identify a legitimate token. To distinguis the illegitimate token 0x208A9... from the legitimate tokens, we had to count the unique addresses in the _from_ and _to_ fields of the transfers. The spam token only had one _from_ address and no duplicate _to_ addresses. 

The table below quantifies this pattern:

| Token Name | Unique From Address | Unique To Address | Address in Both From and To | Total Unique Address |
|------------|---------------------|-------------------|-----------------------------|----------------------|
| CRV        | 590                 | 713               | 443                         | 860                  |
| cvxCRV     | 136                 | 152               | 125                         | 163                  |
| UNI        | 504                 | 689               | 277                         | 916                  |
| LINK       | 1097                | 1627              | 546                         | 2178                 |
| WETH       | 843                 | 851               | 392                         | 1302                 |
| WBTC       | 952                 | 1159              | 665                         | 1446                 |
| 0x208A     | 1                   | 5000              | 0                           | 5001                 |
| 0x471c     | 1                   | 5000              | 0                           | 5001                 |

Of course, transaction data analysis has its limits. The SQUID token, for example, was created by scammers. They leveraged their community to mimic a legitimate token transfer pattern. But then they pulled the run on their token holders and ran off with millions. Additional sub-scores would have been required to expose SQUId as a scam.

This initial test shows that analysis of on-chain data holds promise. 
