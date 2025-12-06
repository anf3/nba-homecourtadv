Home Court Advantages on NBA Game Outcomes: Regular Season vs. Playoffs

This project is intended to analyze the causal effect of having a home court advantage on win probability and scoring differential, and how it differs between the regular season and the playoffs in the National Basketball Association (NBA) using data from _NBA Dataset - Box Scores & Stats, 1947 - Today_ on Kaggle by Eoin A Moore. 
https://www.kaggle.com/datasets/eoinamoore/historical-nba-data-and-player-box-scores/data?select=TeamStatistics.csv

The primary dataset will be Games.csv from the NBA Dataset, and the TeamStatistics.csv will be used as a secondary dataset. Both datasets were cleaned and have been minimized to the begin at the start of the 2015-16 season until the 2024-25 season (not including the 2020-21 COVID year) and an exploratory data analysis with visualizations was conducted (Games_DataAnalysis.ipynb).

Two predictive models have been trained:
  1. Logistic Regression Model
     - Goal: Predict win probability
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


<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         nba_homecourtadv2 and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── nba_homecourtadv2   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes nba_homecourtadv2 a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```


