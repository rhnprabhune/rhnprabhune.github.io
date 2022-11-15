# Project 3 Review

I recently completed [Project 3](https://manan100196.github.io/ST_558_Project3_GroupD/) as a part of my curriculum for **ST 558: Data Science for Statisticians**.
You can find the github repo [here](https://github.com/Manan100196/ST_558_Project3_GroupD)

## What would I have done differently
- Currently, since I am using linear model for predicting, I compare different models using the RMSE values as an error metric. This results in high values of errors on the test set and also I am not sure if that is an appropriate metric for count data. I would have tried to learn about and implement other scoring methods mentioned in this [article](https://stats.stackexchange.com/questions/71720/error-metrics-for-cross-validating-poisson-models). 
- There are a large number of predictor variables in the dataset, some of which are highly correlated. I was able to remove some collinearity using correlation plots and using a 0.8 threshold however I feel that this dataset requires a more extensive EDA to get a better model.
- I am not entirely sure if using PCA with Random Forest was the best idea as we split the predictor space based on some variable. I was unable decide with clear thought process which variables to select (other than correlated ones). I should have probably checked some hypothesis based variable selection methods then applied Random Forest to check if I obtain better results for RMSE on the test set.
- I would have looked into using Cross Validation and implement Random Forest using parallel computing. Training random forest was computationally expensive task and I thought parallel processing might help here. I am not sure if this idea is completely viable here but might look into it in the future.

## Most difficult part
- The response variable in this case was count. Hence I thought of using poisson regression for modelling however, I did not take into account that the counts were reasonably large and therefore a normal model would have worked. After all I did end up using normal model for prediction but for a while I was stuck for finding the correct way of modelling this.
- Variable selection and selecting the model parameters is always a tough job. I feel this was a difficult part of the project which requires more trial and error to fit the model better.  
- Lastly, resolving merge conflicts is a pain as always ! 

## Big take-aways from this project
- Need more clarity when doing EDA based on the type of variables available.
- Model training is computationally expensive and a game of trial and error (Not an illogical game!)
- Variable selection is a crucial step in machine learning pipeline. 