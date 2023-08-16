# MLB_Game_Predictor
Binary classification model that predicts the winner of Major League Baseball games

**To use this model, run the Jupyter Notebooks in this order:**

Model Scoresheet

MLB_Game_Outcome_Live_Wrangling

MLB_Game_Outcome_Live_Modeling

## Target variable
Home_Win: 1 = home team wins game, 0 = away team wins game

## Features
We use 24 features to predict our target variable. These features compare the starting pitchers, each team's collective hitting and relief pitchers, each team's wins, run differential, Pythagorean wins, wins in last 10 and 30 games and ballpark factors.

These features are derived from the perspective of the home team. For example, if the home starting pitcher's SIERA is 4.93 and the away starting pitcher's SIERA is 3.67, SIERA_Diff will be -1.26. If the home team has won 73 games and the away team has won 59 games, Win_Diff would be 14.





