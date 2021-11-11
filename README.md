# NBA-Veteran_Analysis

## Concept
The goal of this project is to help front offices evaluate veterans when adding to their roster to bolster championship contention. I am creating a predictive model to evaluate player decline over the upcoming seasons. The model will apply a variety of player evaluation metrics per season dating back to the 1980s to map player improvement and decline which will be the features. The model will then predict player drop offs for the 2019-2022 seasons using a player decline metric I have created. I will use cross-validation to remove a small subset of player training data for the 40 seasons tracked and apply it to the test data. 

## Definitions
Veterans - aged 30-34. Typically in the latter part of their career but still have a lot to offer. Classfied as bench players, starters, all stars, and superstars based on a combined measurement of WS/48, MPG, and USG%.

Features - ['G', 'MP', 'PER', 'TS%', '3PAr', 'FTr', 'ORB%', 'DRB%', 'AST%', 'STL%',
       'BLK%', 'TOV%', 'USG%', 'OWS', 'DWS', 'WS/48', 'OBPM', 'DBPM', '3P%',
       '2P%', 'FT%', 'Next Cont', 'Player Level'] 

Target = Veteran Value Classifier (involves change in Win Shares and Team Net Rating from current year and next year)

### Why Win Shares?
Win shares is an all encapsulating metric that evaluates the impact of a players shot creation for the number of possessions played (OWS) and their impact on the defensive end based on defensive rating and offensive rating of opponent teams when on the floor (DWS).
### Why Team Net Rating?
While Win Shares can individually measure players impact on winning, basketball is a team sport. If the team is already good, winning may be easier. If a player improves his win shares while the team gets worse, that can highlight how much that player impacts winning while having bad teammates. It is important to measure team net rating along with win shares.

### Model Choice Accuracy
After performing cross-validation with 5 k-folds, we find that RandomForest Classification performs the best. We apply train our data (1997-2019) on this data with a 90/10 split of train/test data. We get an accuracy of 0.679 which is solid considering we only have 822 data points. This model makes predictions on 2021-2022 data with the same set of features. 

## Results
Results shown at the bottom of ml_modeling.ipynb

## Data
Source: 
Kaggle - https://www.kaggle.com/drgilermo/nba-players-stats/version/2?select=Seasons_Stats.csv
Basketball Reference (Roster Continuity, Team Net Rating, etc.)


## Programs
There are three main scripts in this project.
### 1. Player Metrics Notebook
This notebook scrapes data from basketball reference and Kaggle and creates a large data set of players. It applies the necessary contraints and data cleaning to make predictions on. 
### 2. Regression Analysis Notebook
This notebook creates the veteran value metric and applies regression techniques to analyze the distribution of predictions against the features. It also makes educated hypothesis on certain factors that need be explored and makes necessary feature constraints to meet necessary conclusions.
### 3. ML Modeling Notebook
This notebook uses the final data frame to train the model on. It applies cross-validation to evaluate a variety of classification models. It evaluates accuracy of six models, chooses the best performing one, and makes a final prediction on the veteran value class of veterans for the 2021-2022 NBA season.

