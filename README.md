# visualEDAmovieratings

The Descriptive Statistics on Box Office Mojo Ratings

Introduction

The objectives of this project entails the visualization, exploratory data analysis, data science, and conclusive pressentations on movie ratings.
Moreover, this endeavor coincides with Microsoft's operational expansion with regards to cinema and movie goer's high demands for what
type of genres they would watch. The results will provide Microsoft with an in-depth comprehension of what kinds of movies to 
produce for their new movie studio. This project captures the past and current movie trends, categories of movie titles, and along with a 
multitude of other types of ratings. Data collection, mining, cleaning, visualizations, and analysis are utilized in respect to the conclusion
of the data scientific findings of the movie critiques and ratings. Descriptive statistics such as univariate and bivaritate models are
used. I definitely will incorporate other statistical models as well which deals with graphical representations, contingency tables, standard
deviations, time series, etc.

Goals

1. Analyzing the movie ratings, categories of types of flix, box office revenue, number of moviegoers
2. statistical modelling using descriptive statistical visualization
3. drawing conclusions based on past and current types of movies with the most success in theaters and retail/e-commerce sales

Univariate Analysis
After some data cleaning, a univariate analysis was performed on the features. Some findings:

•R-rated movies are the most common by rating.
•Drama movies are the most common by genre.
•Movies are most commonly released on the 1st of the month.
•Movies around 100 minutes in length are the most common.
•Most movies don't have an Oscar-winning actor in the cast.
•Most movies are not directed by an Oscar-winning director.

Bivariate Analysis
Here we compared each of the features in the dataset to the target variable, IMDB rating. Some findings:

•Having an Oscar-winning director in the cast predicts higher ratings.
•However, having an Oscar-winning actor in the cast does not predict higher ratings.
•Documentaries rate higher than feature films.
•Documentaries are the highest-rated genre.
•Comedy is the lowest-rated genre.
•Many movies that are between 77-129 minutes in length rate below 5.6. However, not a single movie longer than 129 minutes rates this low (even though there are many movies longer than 129 minutes).

Statistically-Significant Predictors of IMDB Rating
The analysis found that each of the following have a p-value < 0.0006 when predicting IMDB Rating:

•movie length
•genre
•type ('Feature Film', 'Documentary')
•maturity ('R', 'PG', 'PG-13', 'G')
•best_director ('yes', 'no')

Linear Regression Model
As mentioned in the introduction, it was not feasible to build a high-performing linear regression model from this dataset. First I built a linear regression model that attempts to predict movie ratings using just the 5 significant predictors, but its adjusted R-squared was only 0.2993. Then I decided to take an all-possible-models approach, whereby I built one model for each possible subset of features and kept the one which performed best. This was computationally feasible given that there were just 10 features to choose from (and therefore a mere 2^10=1024 possible models), but the adjusted R-squared only jumped to 0.3127.

What I Learned in Hindsight
I completed this project in 2018. Looking back on it now, with an extra year of experience in data science, I would do a number of things differently, such as:

•Write my code under the functional programming paradigm; a lot of duplication of code could be avoided (for example when building numerous similar ggplot visualizations).
•More appropriately use whitespace in my code to make it more human-readable.
•Use more descriptive variable-naming conventions.
•Remove the empty code block at the very end of the notebook.
•Move the definitions of functions lmp() (which extracts a model's p-value) and all.possible.regressions() from the end of the notebook to the beginning of the notebook (and change the name 'lmp' to something more descriptive).
•Explicitly write ggplot code in the code blocks where the corresponding visualizations are produced. Beforehand though I would build a function which automates as much of the process of creating these plots as possible. (There are 19 such plots and the ggplot code is currently all stuffed into one code block at the end of the notebook.)
•Use TRUE/FALSE for Boolean values rather than 'yes'/'no'.
•Title the 'type' histogram as 'Type' rather than 'Feature Film?', in order to be consistent and descriptive.
•Invest more time in understanding how each movie's genre is determined. Each movie is classified as just one genre, even though on the IMDB website a movie can be classified under many genres.
•If I had access to more data I would like to reanalyze how having a best actor in the cast affects movie ratings. The EDA showed that the effect is minimal, but this is plausibly due to a sample size issue.
