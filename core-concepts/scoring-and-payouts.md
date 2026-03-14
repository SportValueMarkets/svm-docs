# Scoring and Payouts

Whenever a player token is staked, it is eligible for performance related payouts. Payouts are not paid on each event, but they accrue an amount that can be redeemed any time. When a token is staked, the user gets a receipt token. This is a pretty standard way of operating in DEFI and it offers technical implementation advantages but it also offers composability. The staked version of a token can be used elsewhere. A certain amount of the tokens is purchased by the rewards pool from the market (DEX) and is then burned. That allows token holders who didn’t stake their tokens to get some of the rewards indirectly. This also contributes to the price appreciation of the token.<br>

The payout depends on the score of a player and the available funds in the payout pool.  There is a payout amount for each player that is shared by  the token holders.



For a specific game:

Payout(player) = score(player,game) / sumOfAllScores(game) \* payoutFunds(game)



Payout(user, player) = numberOfStakedTokens(user, player) / totalNumberOfTokens(player) \* payout(player)



The score is calculated using a scoring matrix borrowed from fantasy sports. The scoring formula is different for every sport. For football it is:<br>

score = game result score +  attack score + passing score + defending score - errors



The score is also adjusted for different types of players (attacker, defender, midfield, goalkeeper). See the scoring matrices in scoring matrix sections.

In order to calculate the score, the system collects stats from data providers via an Oracle network.

<br>

