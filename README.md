Home Court Advantages on NBA Game Outcomes: Regular Season vs. Playoffs

This project is intended to analyze the causal effect of having a home court advantage on win probability and scoring differential, and how it differs between the regular season and the playoffs in the National Basketball Association (NBA) using data from _NBA Dataset - Box Scores & Stats, 1947 - Today_ on Kaggle by Eoin A Moore. 
https://www.kaggle.com/datasets/eoinamoore/historical-nba-data-and-player-box-scores/data?select=TeamStatistics.csv

The primary dataset will be Games.csv from the NBA Dataset, and the TeamStatistics.csv will be used as a secondary dataset. Both datasets were cleaned and have been minimized to the begin at the start of the 2015-16 season until the 2024-25 season (not including the 2020-21 COVID year) and an exploratory data analysis with visualizations was conducted (Games_DataAnalysis.ipynb).

Two predictive models have been trained:
  1. Logistic Regression Model
     - Goal:Predict win probability
     - Features: homeSeasonWinPct, awaySeasonWinPct, playoffs, homePlayoffInteraction
     - Findings: Home and away team strength are the strong predictors of win probability.
     
  2. Linear Regression Model
     - Goal: Predict scoring differential
     - Features: homeSeasonWinPct, awaySeasonWinPct, playoffs, homePlayoffInteraction
     - Findings: Stronger home teams have a higher advantage in the playoffs, but are hard to accurately predict.
    
Model Training Procedures:
  1. Load Cleaned_Games.csv
  2. Select predictor and target variables
  3. Split dataset (70% -> training, 15% -> validation, 15% to testing)
  4. Initialize regression model (with and without interaction)
  5. Train the model on training dataset
  6. Use the validation dataset to tune the model
  7. Evaluate the model on the test dataset
  8. Save the trained model
