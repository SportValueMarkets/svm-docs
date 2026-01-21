# Token Issuance

The protocol issues crypto tokens (ERC20 on the EVM compatible chains) that represent athletes in different sports (football, basketball, etc) or teams. We can call them player tokens. Their supply is fixed.<br>

How can tokens be introduced to the market? One way is an auction system. But we found it can be hard to bootstrap liquidity with auctions. We are using a bonding curve for the initial token issuance. A bonding curve is a mathematical curve that defines a relationship between price and token supply. We are using the [Bancor formula](https://github.com/relevant-community/bonding-curve/blob/master/contracts/BancorFormula.sol) for the issuance price:



Token Price = Reserve Token Balance / (Token Supply x Reserve Ratio)



The Reserve Ratio determines how sharply a Continuous Token’s price needs to adjust in order to be maintained with every transaction, or in other words, its price sensitivity. This is covered in detail in \[[Bonding Curves](https://yos.io/2018/11/10/bonding-curves/)].



This is what the Bancor curve looks like:

<figure><img src="https://lh7-us.googleusercontent.com/docsz/AD_4nXcxsanS9y1tutqJG1BiAgIexHJw7qY8Aq_634O6pSns2M3buaJu1sddh8q9qwXc-X7liJPveDjDrLUcdrwlR2eq6RmErS3RzT0b2jmXdU-zJRKBANPwztgPgXfKpcKvokv7sJTCVxu2p8alHDLDtwanyuAq?key=lt2UPDordHj2oL48Ch3-Ug" alt=""><figcaption></figcaption></figure>



We introduce differences from the Bancor continuous token issuances. First, Player Tokens are fixed supply. They are not minted on demand. Then there is an issuance period, like an IPO. Once the issuance is terminated, tokens can be traded on a secondary market (DEXes or CEXes). We use the Bancor bonding curve only for token issuance. Proceeds from the token sale and unsold tokens are transferred to the Rewards Pools, Liquidity Pools (for DEXes) and the DAO treasury.



An entity with the permission to issue new tokens (DAO executor) can initiate the issuance of a new athlete token.<br>

Issuance process:

1. A vote is cast about what new Player tokens to issue
2. If all conditions are set (data source is available), the token sale can be initiated
3. 50% of the tokens are offered for sale to the issuance contract. They may not be sold completely if there is a lack of demand.
4. Unsold tokens are split between liquidity pools, reward pools, and DAO treasury
5. The token is listed on the DEX, and liquidity is provided by the treasury
