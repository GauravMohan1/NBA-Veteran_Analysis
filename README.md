# NBA-Veteran_Analysis

## Concept
The goal of this project is to help front offices evaluate veterans when adding to their roster to bolster championship contention. I am creating a predictive model to evaluate player decline over the upcoming seasons. The model will apply a variety of player evaluation metrics per season dating back to the 1980s to map player improvement and decline which will be the features. The model will then predict player drop offs for the 2019-2022 seasons using a player decline metric I have created. I will use cross-validation to remove a small subset of player training data for the 40 seasons tracked and apply it to the test data. 

## Definitions
Veterans - aged 30-34. Typically in the latter part of their career but still have a lot to offer.

Veteran Mins - 35+ players are typically offered vet minimums

Features - TBD 

Target = Decline = (WS(next year) - WS(current year))/(Usage (next year) - Usage(current year))
### Why Win Shares?
Win shares is an all encapsulating metric that evaluates the impact of a players shot creation for the number of possessions played (OWS) and their impact on the defensive end based on defensive rating and offensive rating of opponent teams when on the floor (DWS).
### Why Usage?
Usage represents how much a player is involved in the offensive sets. As a player gets older and turns into a veteran, their role is likely to change causing their usage to lower. We want to factor in usage to make sure the drop in Win Shares isn’t skewed.

