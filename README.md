# Summary
In this project I will take face value ticket prices from TicketMaster for concerts in the largest US markets, as well as prices for tickets on resale markets (TicketMaster resale, SeatGeek), along with data on artist and genre popularity to predict markups on secondhand concert tickets.

# Question
What determines the price of a concert ticket in the secondary market? Understanding this question can help artists and tour promoters more accurately price tickets and gage demand for tickets.
Consumers may also find such a tool helpful in determining when ahd how to buy and sell tickets

# Solution

## 1. Data Gathering
I gather data from 4 sources:
1. Ticketmaster API (Face value price information)
2. SeatGeek API (Resale value price information)
3. Stubhub API (Resale value price information)
4. Spotify (Popularity information on artists)

The concerts data is matched between sources based on datetime and venue name, under the assumption that a venue only has a single event at a given time. I include a few notes on how the venues were matched in the 'Venue Matching Notes' notebook.

## 2. Data Exploration and Feature Engineering
    1. Import data, initial cleaning and feature engineering
    2. Feature Summaries
      1. Continuous variables
      2. Categorical Variables
      3. Category Consolidation
    3. Data Exploration
      1. Scatterplots (Spotify info, ticket listings, time information)
      2. Venue State
      3. Day of Week
      4. Genre and Subgenre
      5. Artist Count
      6. Promoter
      7. Resale Ticket Source  
## 3. Statistical Analyses
    1. Continuous Variables - Pearson & Spearman Correlation
    2. Categorical Variables - T-tests, ANOVA F-tests, and Pair Tukey tests

See the ["Statistical Analyses"](3.Statistical_Analyses.md) report for visualizations and findings
## 4. Machine Learning
1. Data Preprocessing
2. Linear Regression
    1. Standard Linear Regression
    2. ElasticNet
    3. Lasso
    4. Comparison of Methods
3. Classification
    1. Variable & Function Setup
    2. Classifier Evaluation with 3 & 4 Bins
    3. Learning Curves
    4. Feature Importance Rankings
    5. Hyperparameter Tuning
    6. Model Ensembling and Comparison on Test Set
    7. Neural Net with Keras and Tensorflow
## 5. Final Analysis
  1. ["Final Report"](https://github.com/yiaktan/Secondhand_Concert_Tickets/blob/master/Cap1%20Final%20Report.pdf)
  2. ["Medium Post --Published on Towards Data Science"](https://towardsdatascience.com/how-much-is-your-concert-ticket-really-worth-382a8d38333)
