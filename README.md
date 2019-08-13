# Linear Regression for IMDB Movie Ratings

The project can be seen in the .ipynb file.

### Introduction
This is the capstone project for Coursera's Linear Regression and Modeling MOOC. We are provided with a dataset of 651 randomly-selected movies from IMDB and asked to explore the data and build a linear regression model to predict movie ratings. It turns out that it was infeasible to build a high-performing linear regression model with this dataset, so identifying the statistically-significant predictors of movie ratings was promoted to primary goal.

### Goals
•Primary: To determine which variable(s) can be used to predict IMDB movie ratings (looking at p-values). <br />
•Secondary: To build a linear regression model that predicts IMDB movie ratings (looking at adjusted R-squared).

### Univariate Analysis
After some data cleaning, a univariate analysis was performed on the features. Some findings: <br />
•R-rated movies are the most common by rating. <br />
•Drama movies are the most common by genre. <br />
•Movies are most commonly released on the 1st of the month. <br />
•Movies around 100 minutes in length are the most common. <br />
•Most movies don't have an Oscar-winning actor in the cast. <br />
•Most movies are not directed by an Oscar-winning director.

### Bivariate Analysis
Here we compared each of the features in the dataset to the target variable, IMDB rating. Some findings: <br />
•Having an Oscar-winning director in the cast predicts higher ratings. <br />
•However, having an Oscar-winning actor in the cast does not predict higher ratings. <br />
•Documentaries rate higher than feature films. <br />
•Documentaries are the highest-rated genre. <br />
•Comedy is the lowest-rated genre. <br />
•Many movies that are between 77-129 minutes in length rate below 5.6. However, not a single movie longer than 129 minutes rates this low (even though there are many movies longer than 129 minutes).

### Statistically-Significant Predictors of IMDB Rating
The analysis found that each of the following have a p-value < 0.0006 when predicting IMDB Rating: <br />
•movie length <br />
•genre <br />
•type ('Feature Film', 'Documentary') <br />
•maturity ('R', 'PG', 'PG-13', 'G') <br />
•best_director ('yes', 'no')

### Linear Regression Model
As mentioned in the introduction, it was not feasible to build a high-performing linear regression model from this dataset. First I built a linear regression model that attempts to predict movie ratings using just the 5 significant predictors, but its adjusted R-squared was only 0.2993. Then I decided to take an all-possible-models approach, whereby I built one model for each possible subset of features and kept the one which performed best. This was computationally feasible given that there were just 10 features to choose from (and therefore a mere 2^10=1024 possible models), but the adjusted R-squared only jumped to 0.3127.

### What I Learned in Hindsight
I completed this project in 2018. Looking back on it now, with an extra year of experience in data science, I would do a number of things differently, such as: <br />
•Write my code under the functional programming paradigm; a lot of duplication of code be avoided. <br />
•More appropriately use whitespace in my code to make it more human-readable. <br />
•Use more descriptive variable-naming conventions. <br />
•Remove the empty code block at the very end of the notebook. <br />
•Move the definitions of functions lmp() (which extracts a model's p-value) and all.possible.regressions() from the end of the notebook to the beginning of the notebook (and change the name 'lmp' to something more descriptive). <br />
•Explicitly write ggplot code in the code blocks where the corresponding visualizations are produced. Beforehand though I would build a function which automates as much of the process of creating these plots as possible. (There are 19 such plots and the ggplot code is currently all stuffed into one code block at the end of the notebook.) <br />
•Use TRUE/FALSE for Boolean values rather than 'yes'/'no'. <br />
•Title the 'type' histogram as 'Type' rather than 'Feature Film?', in order to be consistent and descriptive. <br />
•Invest more time in understanding how each movie's genre is determined. Each movie is classified as just one genre, even though on the IMDB website a movie can be classified under many genres. <br />
•If I had access to more data I would like to reanalyze how having a best actor in the cast affects movie ratings. The EDA showed that the effect is minimal, but this is plausibly due to a sample size issue.


