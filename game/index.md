---
order: B
icon: rocket
expanded: true
---
# The Game

=== 1. Choose a team/project
Upon navigating to https://volumewars.app, the first step is to pick and join a team.
Each team on Volume Wars is a project with their own token on Binance Smart Chain.
Switching teams afterwards is not allowed, so choose wisely!
The team selection requires submitting a transaction, which will cost a small amount of gas.

=== 2. Attack another team to earn XP and put damage points on the enemy
Now for the fun part.
First, select the team you want to attack. Second, choose the size of your attack in BNB:
There are four attack *tiers*, which are based on the amount of BNB you will spend when choosing them.

Your enemy receives Damage Points equivalent to the BNB you spent, while you earn the same amount in experience points (XP).
You will receive a booster pack corresponding to the tier of your attack. The higher the tier, the greater the rewards they yield.
Tier 1 booster packs have the lowest rewards, Tier 4 the highest.
You will always receive a booster pack, but not all packs contain rewards.

=== 3. Receive booster packs which contain unique collectable rare and common NFTs
Higher damage yields higher rewards generated as higher tier booster packs.
Booster packs are unique to volume wars and contain one of several substrate NFTs that, when combined together,
allow the user to obtain BNB captured within the game. The opportunity to collect and trade these NFTs within the ecosystem to complete 
the set is the overall objective to fully capture this value potential within Volume Wars.

=== 4. Unwrap your booster packs and retrieve your NFTs
Once you earn booster packs by playing the game, you must "claim" them before being able to open them.
This is a two step process. After claiming, you will have to wait a few minutes before automatically
receiving your claimed packs back, which are then ready to be opened.

We leverage Chainlink's VRF to generate random numbers for the rewards.
The way the random numbers are selected inherently requires two transactions for
security reasons, which is why the process happens in two steps, claiming, and opening.
Learn more about it through their documentation: https://docs.chain.link/docs/chainlink-vrf/

There is a fee for claiming, which is paid to the Chainlink VRF contract.
All current unclaimed boosters are processed together in a single transaction,
and the fee you pay does **not** change depending on the number of packs included in it.
In order to reduce your costs you can wait until you have many booster packs before claiming them.

Chainlink VRF is widely considered as an industry standard in randomness on the blockchain.

Once the next season starts, minting NFTs from previous seasons becomes impossible.
If you have unopened or unclaimed booster packs, these will always mint NFTs from the **current** season regardless of
when the booster packs were obtained.

The only exception is Legendaries. Legendaries from previous seasons can be forged after their season has ended, however
they require you to own the full set of NFTs from the season they are from. Hence, they are limited by the number of rare and common
NFTs minted during that season.

=== 5. Complete a season's set to forge a Legendary and collect rewards
Once you complete a particular season's set of 7 NFTs, you can sacrifice them to forge that season's *Legendary*.
This requires one of each of the **4 common** and **3 rare** cards from the **same season**.

Legendaries can be staked, receiving BNB rewards corresponding to a portion of each future season's revenue.
After 52 seasons (counted from the Legendary's own season), they expire, and no longer receive rewards. Expired Legendary NFTs are automatically unstaked.

===

!!!warning
IMPORTANT: YOU CANNOT MIX NFTS ACROSS MULTIPLE SEASONS TO MINT A LEGENDARY. YOU NEED TO OWN THE FULL SET FROM A PARTICULAR SEASON
!!!

#### Examples
Here are some examples for when a player may forge a legendary NFT:
!!!success
Player 1 has the following NFTs in their possession

- 1 common NFT #1 from season 3
- 1 common NFT #2 from season 3
- 1 common NFT #3 from season 3
- 1 common NFT #4 from season 3
- 1 rare NFT #5 from season 3
- 1 rare NFT #6 from season 3
- 1 rare NFT #7 from season 3

**This player can forge a legendary NFT for season 3.**
!!!
!!!danger
Player 2 has the following NFTs in their possession:

- 1 common NFT #1 from season 2
- 1 common NFT #2 from season 3
- 1 common NFT #3 from season 1
- 1 common NFT #4 from season 3
- 1 rare NFT #5 from season 4
- 1 rare NFT #6 from season 3
- 1 rare NFT #7 from season 2

**This player cannot forge a legendary NFT.**
!!!
!!!danger
Player 3 has the following NFTs in their possession:

- 9 common NFT #1 from season 3
- 5 common NFT #2 from season 3
- 4 common NFT #3 from season 3
- 5 common NFT #4 from season 3
- 9 rare NFT #5 from season 3
- 0 rare NFT #6 from season 3
- 3 rare NFT #7 from season 3

**This player cannot forge a legendary NFT.**
!!!