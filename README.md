# Linear Regression for IMDB Movie Ratings

You can see the project at the following link:
https://nbviewer.jupyter.org/github/nateofspades/Linear-Regression-for-IMDB-Movie-Ratings/blob/master/ProjectIMDB.ipynb

## Summary
This is the capstone project for Coursera's Linear Regression and Modeling MOOC. We are provided with a dataset of 651 randomly-selected movies from IMDB and asked to explore the data and build a linear regression model to predict movie ratings. It turns out that it was infeasible to build a high-performing linear regression model with this dataset, so identifying the statistically-significant predictors of movie ratings was promoted to primary goal.

### Goals
•Primary: To determine which variable(s) can be used to predict IMDB movie ratings (looking at p-values). <br />
•Secondary: To build a linear regression model that predicts IMDB movie ratings (looking at adjusted R-squared).

### Univariate Analysis
After some data cleaning, a univariate analysis was performed on the features. Some findings:
•R-rated movies are the most common by rating.
•Drama movies are the most common by genre.
•Movies are most commonly released on the 1st of the month.
•Movies around 100 minutes in length are the most common.
•Most movies don't have an Oscar-winning actor in the cast.
•Most movies are not directed by an Oscar-winning director.

### Bivariate Analysis
Here we compared each of the features in the dataset to the target variable, IMDB rating. Some findings:
•Having an Oscar-winning director in the cast predicts higher ratings.
•However, having an Oscar-winning actor in the cast does not predict higher ratings.
•Documentaries rate higher than feature films.
•Documentaries are the highest-rated genre.
•Comedy is the lowest-rated genre.
•Many movies that are between 77-129 minutes in length rate below 5.6. However, not a single movie longer than 129 minutes rates this low (even though there are many movies longer than 129 minutes).

### Statistically-Significant Predictors of IMDB Rating
The analysis found that each of the following have a p-value < 0.0006 when predicting IMDB Rating:
•movie length
•genre
•type ('Feature Film', 'Documentary')
•maturity ('R', 'PG', 'PG-13', 'G')
•best_director ('yes', 'no')

### Linear Regression Model
As mentioned at the beginning of this README, it was not feasible to build a high-performing linear regression model from this dataset. First I built a linear regression model that attempts to predict movie ratings using just the 5 significant predictors, but its adjusted R-squared was only 0.2993. Then I decided to take an all-possible-models approach, whereby I would build one model for each possible subset of features. This was computationally feasible given that there were just 10 features to choose from (and therefore a mere 2^10=1024 possible models), but the adjusted R-squared only jumped to 0.3127
