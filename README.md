### EXPLANATORY ANALYSIS

For the FIFA21 project, we were presented with a table of data regarding professional football player’s personal, professional and skills information. The goal was to build a model so in the future, we could predict the overall player’s rating score.
Our group first imported the different packages to be able to: get, read and work with the data.
After reading the data, we started cleaning the data by dividing the multiple columns into 2 groups of 51 (out of the 102), so it would be easier to check its values and work with a smaller list.
When cleaning the data, we performed the following actions:
- Standardized the column names by lowering its cases and replacing the spaces with underscores
- Noticed the relationships with the different variables: dropped the ones that we tought were going to be redundant for our model, kept the variables we thought would be relevant.

    ####  Dropped variables:
    
- Unnamed: most likely a copy of the ID variable. Noticed it with “Group by” function
- Club related variables: we got rid of all club related variables like Team & Contract, Joined, Loan Date End, etc.
- Position: kept the BP value as it added more value to our model
- Dropped all football skills variables: all mostly included in Base Stats and Total Stats

    #### Kept values:
- Height, Weight, Foot: tought physical attributed could be a factor which impacts the overall rating of a player (ova)
- Base Stats & Total Stats: highly correlated with ova.
- Variables that describre player money valuation: could be related that the most a player is paid is because it is correlated with its ova.
- BP & player best position score: the players best position needs to be in the model because the ova is most likely coming from the player best position rating score.

    #### Divided the numerical and categorical variables and started the following EDA steps:
- Transforming numerical types stored as categorical into numerical variables by defining functions and pandas commands. Example: removing euro symbols
- Visualization analysis: pairplot, displots, boxplots and heatmap.
- Creation of new data frames with cleaned values
Concatenated each cleaned variable into a final data frame.
- Checked correlations between final variables using heatmap to decided whether to drop any other before creating the prediction model or not.

    #### Creation of the prediction model.
- X-y split by defining “ova” as target variable
- Build the model applying the linear regression method
- Train-test split to fit the model with our final data
Model validation.
- Calculated R2, MSE, RMSE and MAE
Noticed our model was better than expected with a model score of 0.79 and mean absolute error of 2.4.

    #### However, we tried to improve the model prediction by:
- Normalizing the numerical variables with MinMaxScale
- Introduced relevant categorical variables like international rating(?) and BP
- Introduced a key numerical variable by using panda’s melt function: players best position score
- After repeating the prediction model steps, we reached a model score of 0.98 with a mean absolute error of 0.8(?).
In conclusion, it is clear that the overall rating of a player depends mostly on the players best position score. If we just used the total and base stats we would have been able to predict a players overall rating but not super accuratelly. On the other hand, physical and personal information values were not useful when trying to predict a player’s ova.
In the future, if we would like to build a new model, we should focus on the players best position score which would lead to lesser use of redundant variables, speeding up the computer prediction model results.
