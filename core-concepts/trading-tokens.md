# Trading Tokens

SVM uses both a Bonding Curve and an AMM (Automated Market Maker) because they serve two completely different stages of a token's lifecycle: the Birth (fair launch) and the Adult Life (open market trading).

Think of the Bonding Curve as a "protected nursery" for new tokens and the AMM as the "open ocean" once they are strong enough to swim on their own.

### 1. The Bonding Curve: The "Nursery"

When a new player token is first created, it lives exclusively on a bonding curve. See [Token Issuance](token-issuance.md) section which describes it in detail.

### Why use a Bonding Curve?

* No Initial Liquidity Needed: In a traditional launch, a creator must provide thousands of dollars in "seed" liquidity to start a liquidity pool. With a bonding curve, the smart contract is the liquidity. You buy from the contract and sell back to the contract.
* Fair Launch: Everyone starts at the same price point on the curve. Early buyers get a better price, but the price discovery is transparent and automated.
*   Buyers have the ability to sell back (for a feee) if they need to, even before the token graduates.



### 2. The AMM: The "Open Ocean" (Post-Graduation)

Once enough people buy the token and it hits a defined market cap (Around 100,000$), the bonding curve "completes" or "graduates." At this point, the token moves to an AMM (initially Uniswap, and then any other exhcnage).

### Why move to an AMM?

* Decentralized Trading: Once on an AMM, the token can be traded on any DEX (Decentralized Exchange) or even centralised exchanges willing to list it.
* Permanent Liquidity: SVM takes the USDC raised during the bonding curve phase, pairs it with the remaining tokens, and deposits it into the AMM.
* Standardization: Most of the DeFi world (bots, charts, wallets) is built to read AMM pools. Moving to an AMM makes the token "official" and compatible with all crypto tools.
