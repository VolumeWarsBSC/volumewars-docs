---
order: F
icon: flame
---
# Legendary Math

We developed an algorithm in order to estimate the expected number of legendaries we expect to be created during a season given the season's expected volume and the odds of obtaining a rare with an attack.

We assume that all attacks are Tier 4, the highest and most BNB-efficient attack tier for obtaining rare cards.

We used this algorithm in order to set the *model odds* in the **Difficulty Adjustment** contract.
These *model odds* correspond to a specific *model volume*, and given a season with that much volume, these odds should result in an expected number of legendaries during that season that was decided when generating the model values.

The current model odds and volume are tuned to **~3.6 legendaries** per season.

## Difficulty Adjustment

The Difficulty Adjustment contract is called every time a new season is opened in order to update the odds of getting rare cards.

It calculates the **moving average volume** from the past 5 seasons in order to estimate the next season's expected volume.
Comparing this expected volume with the model volume, it scales the model odds up and down proportionally to the ratio of volumes, in order to preserve the same expected number of legendaries per season the model odds were tuned for.

If the moving average volume increases, the odds will decrease, and vice versa. The purpose is analogous to that of a mining difficulty adjustment algorithm, aiming to ensure the number of rewards (legendaries) created in a given time period (season) remains **constant**.

!!!
Example: The moving average of volume is twice the model volume. The odds of obtaining a rare will be halved by the difficulty adjustment contract once the new season starts.
!!!

## Estimation Algorithm

In order to know how many legendaries we expect to be generated in a particular season, we only need that season's volume, and the chances of obtaining a rare card NFT on each attack.

To mint a Legendary NFT, a player must complete a season's NFT set, which means collecting at least one of each of the cards numbered from 1 to 7, all from the same season. 5 to 7 are the rares. 1 to 4 are commons.

The chances of obtaining particular commons do not have a significant impact on the creation of legendaries.
Therefore we treat obtaining a common as "not getting a rare". We don't care about which commons players are getting or how many they are getting.
Once enough rares have been generated, there will be more than enough commons, and the probability of a player obtaining all 3 unique rares and not having enough commons to complete the season's set is vanishingly small.

We also assume that every attack is a Tier 4. Therefore volume is expressed in number of attacks rather than BNB. In order to convert that to BNB, simply multiply it by the cost of a Tier 4 attack (0.12 BNB at the time of writing).

```Python
from itertools import combinations_with_replacement
from collections import Counter
from math import factorial

def legendaries_per_season(n_attacks, p):
  n_attacks_factorial = factorial(n_attacks)

  # will contian the relative probability of getting any number of legendaries (full sets of rares) in this season
  # mapping n_sets => probability
  n_sets_p = {}
  # 1, 2, 3 represent rares 5, 6, 7; 4 represents any common card
  combinations = combinations_with_replacement([1, 2, 3, 4], n_attacks)
  # iterate over every possible combination of cards drawn, each combination is one way the season could play out
  for combination in combinations:
    # count how many cards of each type we got
    count = Counter(combination)

    # the number of full sets of 3 different rares that are in this combination
    # which is also the number of legendaries that will be created
    n_sets =  min([count[1], count[2], count[3]])

    # the relative probability of this a combination appearing, given the chance of rares vs commons and the number of attacks
    prob = n_attacks_factorial/(factorial(count[1]) * factorial(count[2]) * factorial(count[3]) * factorial(count[4])) * (p/3)**(count[1] + count[2] + count[3]) * (1-p)**count[4]

    # Add this probability to the total probability for getting this number of sets/legendaries
    n_sets_p[n_sets] = n_sets_p.get(n_sets, 0) + prob

  expected_legendaries = 0
  # We get the number of expected legendaries by multiplying each possible number of legendaries (0, 1, 2, etc) by the probability of it occurring, and adding them all together
  for n_sets, prob in n_sets_p.items():
    expected_legendaries += n_sets*prob

  return expected_legendaries
```

