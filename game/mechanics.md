---
order: A
icon: cpu
---
# Game Mechanics

Volume Wars is designed to provide the most rewards the early adopters.
This is achieved by adjusting game variables such as reward chances and prize pool percentage allocation.
Currently the probabilities are balanced to ensure minting a legendary costs 7.2 BNB worth of attacks on average,
but this number will increase over time while remaining sensitive toward adoption of the protocol.

!!!primary
25% of attack volume in BNB is distributed among Legendary holders in the form of staking rewards.
The more legendaries there are, the less yield there is for each individual Legendary.
In the long term, we want to adjust the difficulty of obtaining a Legendary such that on average one Legendary is minted per season.
These NFTs expire and are unstaked automatically after 52 seasons, so the revenue would ideally be split between around 52 NFTs at some point in the future.

In practice there is no guarantee as this is probabilistic and it depends on how much volume is generated.
However more volume results in more rewards to split among holders.

Starting out we have implemented a percentage decrease in the odds to obtain a 
legendary NFT as adjusted weekly and influenced by protocol volume.
!!!

_Note that each season is open for a period of one week._

#### Examples

If 25 BNB volume per week then then chance to obtain a legendary decrease by 33.33% the current rate every week until it is only possible to obtain 1 legendary NFT dropped during the season.

+++ Week 1
1:20 odds per rare dropped @ 0.12 BNB per attack
+++ Week 2 
1:30 odds per rare dropped @ 0.12 BNB per attack
+++ Week 3
1:45 odds per rare dropped @ 0.12 BNB per attack
+++ Week 4
1:68 odds per rare dropped @ 0.12 BNB per attack
+++ ...
_etc..._
+++

If 50 BNB volume per week then chance to obtain a legendary decreases by 28.57% the current rate every week until it is only possible to obtain 1 legendary NFT dropped during the season.

+++ Week 1
1:20 odds per rare dropped @ 0.12 BNB per attack
+++ Week 2
1:28 odds per rare dropped @ 0.12 BNB per attack
+++ Week 3
1:39 odds per rare dropped @ 0.12 BNB per attack
+++ Week 4
1:55 odds per rare dropped @ 0.12 BNB per attack
+++ ...
_etc..._
+++

If 100 BNB volume per week then chance to obtain a legendary decreases by 16.67% the current rate every week until it is only possible to obtain 1 legendary NFT dropped during the season.

+++ Week 1
1:20 odds per rare dropped @ 0.12 BNB per attack
+++ Week 2
1:24 odds per rare dropped @ 0.12 BNB per attack
+++ Week 3
1:29 odds per rare dropped @ 0.12 BNB per attack
+++ Week 4
1:34 odds per rare dropped @ 0.12 BNB per attack
+++ ...
_etc..._
+++

If more than 100 BNB volume per week then chance to obtain a legendary decrease by 9.09% the current rate every week until it is only possible to obtain 1 legendary NFT dropped during the season.

+++ Week 1
1:20 odds per rare dropped @ 0.12 BNB per attack
+++ Week 2
1:22 odds per rare dropped @ 0.12 BNB per attack
+++ Week 3
1:24 odds per rare dropped @ 0.12 BNB per attack
+++ Week 4
1:27 odds per rare dropped @ 0.12 BNB per attack
+++ ...
_etc..._
+++

!!!Primary
    It is possible that the sudden change in volume from week to week could influence our decision to increase or decrease the rewards as necessary.
    We are developing a difficulty adjustment algorithm based on past volume, and we aim to hand its management over to a DAO in the future.
!!!