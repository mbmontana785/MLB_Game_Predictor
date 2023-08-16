# MLB_Game_Predictor
Binary classification model that predicts the winner of Major League Baseball games

**To use this model, run the Jupyter Notebooks in this order:**

Model Scoresheet

MLB_Game_Outcome_Live_Wrangling

MLB_Game_Outcome_Live_Modeling

## Target variable
Home_Win: 1 = home team wins game, 0 = away team wins game

## Features
We use 24 features to predict our target variable. These features compare the starting pitchers, each team's collective hitting and relief pitching, each team's wins, run differential, Pythagorean wins, wins in last 10 and 30 games and ballpark factors.

These features are derived from the perspective of the home team. For example, if the home starting pitcher's FIP is 4.93 and the away starting pitcher's FIP is 3.67, FIP_Diff will be -1.26. If the home team has won 73 games and the away team has won 59 games, Win_Diff would be 14.

## Data Wrangling
We scrape our data from [RotoGrinders](https://rotogrinders.com/), [FanGraphs](https://www.fangraphs.com/) and [Baseball Reference](https://www.baseball-reference.com/).

We take data on everyone who has pitched this season from FanGraphs. We use RotoGrinders to identify that day's starting pitchers and merge it with the relevant observations on FG. We also take the team hitting and bullpen data from FanGraphs. We use Baseball Reference for our win-related features.

## Model iteration
Our final dataset has 4,312 rows and 24 columns, not including the target variable.

These are the test scores for the models we tried:

![Visualization showing test scores of each model we tried.](C:\Users\Owner\Sports Betting\MLB_Game_Outcome\Model_Viz.png)




