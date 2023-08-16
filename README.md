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

All the observations are from the 2021 and 2022 Major League Baseball seasons. Not every game is included, as we had to drop doubleheaders (further explanation on that in the notebooks) and games with missing data.

## Data Wrangling
We scrape our data from [RotoGrinders](https://rotogrinders.com/), [FanGraphs](https://www.fangraphs.com/) and [Baseball Reference](https://www.baseball-reference.com/).

We take data on everyone who has pitched this season from FanGraphs. We use RotoGrinders to identify that day's starting pitchers and merge it with the relevant observations on FG. We also take the team hitting and bullpen data from FanGraphs. We use Baseball Reference for our win-related features.

## Model iteration
Our final dataset has 4,312 rows and 24 columns, not including the target variable.

The train-test split was 80/20.

These are the test scores for the models we tried. The red dotted line indicates that the home team won 53.9 percent of the games in our dataset:

![Model_Viz](https://github.com/mbmontana785/MLB_Game_Predictor/assets/53095233/4d9b63ad-030f-4054-982a-4bf15e58a4e1)

We decided on Logistic Regression with the regularization parameter set at C=0.001. The accuracy on the test set was 57.4 percent.

Technically, our Bagging Classifier (with Logistic Regression as the base model) performed better with 57.6 percent accuracy. We updated our model performance dictionary manually and must have mistakenly typed a lower number. We should have written a function that updated the dict. Live and learn! 

Since we've been using Logistic Regression to predict the live games, we're staying with that.

## Live predictions
We began using our model to make live predictions on Aug. 3, 2023.

Through Aug. 15, the model's accuracy rate for live games was 58 percent (91 correct predictions out of 157 games).



