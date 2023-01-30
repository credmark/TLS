## Score Composition

- a token characteristic,
- a token behavior,
- a characteristic of the entity which issued the token, or
- a behavior of this issuing entity.

Sub-scores could be simple and binary, or complex and non-binary.

Here are a few examples.



Token characteristic sub-score example
We might have a sub-score for a token’s supply.

We could, for example, say that a supply (a) between 1 and 10,000 or (b) greater than 10 billion is “abnormal”. We could assign a sub-score of 0 to indicate an “abnormal” supply and 1 to indicate a “normal” supply.

Or we could be more subtle and define degrees of “normalcy”.

Ultimately, this sub-score would be normalized to values between 0 and 10.
Token behavior sub-score example
We might have a sub-score for token distribution patterns. Excessive concentration or excessive scattering might produce negative sub-scores while more standard distribution patterns might produce positive sub-scores.

Again, those would have to be normalized before being used to produce the final TLS.
Entity characteristic sub-score example
An DAO whose founders and contributors are all anonymous might produce a poor sub-score, for example, whilst a regulated entity like Coinbase might produce a more positive sub-score.
Entity behavior sub-score example
An entity that sold $25M of tokens but hasn’t updated its website for two years might generate a negative sub-score, while an entity that consistently delivers on its roadmap might produce a more positive sub-score.
Producing the TLS from sub-scores
Some sub-scores are more important than others, so they will be given additional weight in the final calculation. Those weights are to be proposed and debated as the sub-scores are defined.

Once sub-scores are weighted, they are simply averaged.

- Value-based

- Non-value based

Graph model about a token's utility from transaction history.




### Category score

The

### Score update

Though we have frequency


### Final score

The final score is a composition of scores from categories

Some categories could have overriding effect to the final score for events like exploited and bankrupcy.


### Score explaination

The score is mapped


Good token: lots of internal flows
Bad tokens: cradle to death, only transfers

Swap, lending, stable coin

Related to stablecoins: DAI, USDT, USDC, BUSD.

Value in exchange:

- Transaction fee: does not matter as same transaction fee for any amount

- How to recognise one swap transaction


Distribution of transaction amount
Distribution of new address in transaction
Percentage in Active volume

No mint and burn, only transacted volume

Associated gas fees

WETH, AAVE, UNI, WBTC, 3CRV

Weekly emission
