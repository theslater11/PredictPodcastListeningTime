# Predict Podcast Listening Time

Our goal is to use machine modeling to predict the amount of time an individual listener will listen to any given podcast when being given the data listed below:

## Column Breakdown

id - A unique listen.
-- A unique identifer. This column will need to be excluded from the training data and included in the test data

Podcast_Name - Name of the Podcast which produces individual episodes
-- A very useful catagory to use in analysis and cleaning. Unfortunetly using it would cause our model to become a lot less general and risk overfitting. I decided to keep it out.

Episode_Title - Order in which the episode was released
-- An interesting column, but had zero predictive qualities.

Episode_Length_minutes - The length, in minutes, of the uploaded podcast
-- An extermely high correlation with Listening_Time show this is a column to keep and 

Genre - main type of content discussed on the program
-- I used this column frequently in my multivariate analysis to visualize changes in other dependent variables. I was not able to find any value in keeping the column so I left it out.

Host_Popularity_percentage - popularity of the host (in%)
-- This was the most challanging column to evaluate. The conclusion I came to was that the rows with higher values in this column did have higher listening ratios, but I did not observe this consistently. I also found that they had a higher chance of positive sentiment. I believe that by including sentiment, I can capture the variance seen in this column and can exclude it.

Publication_Day - Day of the week the podcast episode was published
-- This column did not show any predictive capability

Publication_Time - what time of the day the podcast episode was published
-- This column did not show any predictive capability

Guest_Popularity_percentage - popularity of the podcasts guest(in%)
-- I was not able to prove any significant increase

Number_of_Ads - number of ads aired during the episode
--  This column was shown across multiple comparisons to have an impact on Listening_Time. Less Ads = More Listening time. This column is included.

Episode_Sentiment - sentiment derived from comments on the podcast
-- Positive sentiment did have an effect on Listening_Time. I used ordial encoding to assign Positive(1), Neutral(0), and Negative(-1) values to include this column in our model.

Listening_Time_minutes - Amount of time each id spent listening to a podcast episode 
-- Target Column that our model must predict

The final result will match the id of the test data to a predicted listening time.

## Model Evaluation

I trained 4 different models, 1 Linear Regression model & 3 ensemble models(Decision Tree, Random Forest, & XG Boost), and tuned hyperparameters for each using GridSearch. 

Performance:

Linear Regression RMSE: 13.37

Regressive Tree RMSE: 13.31

Tuned Random Forest RMSE: 13.26 *Best Model*

Tuned XGBoost RMSE: 13.31