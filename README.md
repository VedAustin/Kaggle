# ~Requires Documentation~

# Kaggle - Facebook Data Science Competition (https://www.kaggle.com/c/facebook-v-predicting-check-ins)

The goal is to predict where the user is checking in given (x,y) coordinates, accuracy (related to coordinates) and a transformed time stamp

I have approached this problem by using a combination of KNN, KDE, ensemble of models (two for now) and a lot of feature engineering. This was one of the most interesting problems as popular classification algos do not work well here as there are 100K types.

To offset the disadvantage of accessing cloud based tools or purchasing expensive hardware, as with any large dataset, I randomly sample 1% of the entire data set and use this sampled data set to perform exploratory data analysis, feature engineering and testing hypothesis. In this compeition, I explored the relationship between x,y coordinates and accuracy and noticed that the range of x values for a given location vairied significantly compared to y values. Consequently when I performed KNN search, I used this information along with the corresponding accuracy value, to help reduce the choice to top 20 most likely `place_id`. I then used other features (derived from feature engineering process of the time stamp) and built kernel density estimates for each of the time derived features to whittle down the top 20 list to top 5 most likely. 
