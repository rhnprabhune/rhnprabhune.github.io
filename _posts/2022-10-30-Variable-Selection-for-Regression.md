# Variable Selection for Regression

## Need for variable selection
When creating a data model, the selection of the variables is extremely important to improve the accuracy of the model. However while creating the model one doesn’t know the variables which should be included and those that should be discarded. The response variable y could depend on a number of Independent variables x1,x2,x3,….xp. These number of variables are often too large to be considered in a statistical model.  
Other than that a huge number of variables could lead to addition of unnecessary noise and lead to **over-fitting** (Over-fitting is when the model describes the random errors and noise instead of just describing the underlying relationship). One must also consider that there is cost associated to measuring the predictors and hence variable selection would save the cost if the model is used for prediction.

## Methods for variable selection  
### Selection Procedures  

1. **Forward Selection** : It is A stepwise variable selection procedure in which variables are sequentially entered into the model. It starts with no variables in the model. For each variable not in the model, the extent of the variable’s contribution is calculated, and the largest contributing variable is selected for entry into the equation. The variable is entered into the equation only if it satisfies a specified criterion for entry. This process is repeated until no variables meet the entry criterion.

2. **Backward Elimination**: It is the opposite of Forward selection in which the model initially has all the variables included and then they are sequentially removed. The variable with the smallest partial correlation with the dependent variable or in other words whose contribution is the least is first considered for removal. If the criteria for elimination is met then the variable is removed. This process is also repeated until all the insignificant variables are removed.

3. **Stepwise**: Stepwise is a combination of forward selection and backward Elimination except that the variables added at a step don’t necessarily stay Stepwise search checks going both backwards and forwards at every step. It considers the addition of any variable not currently in the model, as well as the removal of any variable currently in the model.

4. **Regularization**: In regularization we shrink the coefficient estimates towards zero. This technique discourages learning a more complex or flexible model, so as to avoid the risk of over-fitting. There are two main types of regularization techniques: Ridge Regularization and Lasso Regularization.  
&nbsp;&nbsp;&nbsp;&nbsp;4.1 Ridge Regression: Adds penalty equivalent to the sum of the squares of the magnitude of coefficients.  
&nbsp;&nbsp;&nbsp;&nbsp;4.2 Lasso Regression: Adds penalty equivalent to the sum of the absolute values of coefficients.   
In the cost function we get an additional term of regularization parameter (Lambda λ). This is hyperparameter, the value for which can be set by the user. The higher the value of λ, the higher penalty we give to the coefficients which results in the smaller value of coefficients. In this way we can reduce the values of the coefficients for higher order terms in the cost functions which results in simpler models less prone to over-fitting.

### Principal Component Analysis
While this is not directly related to variable selection but it plays an important role in dimensionality reduction. Principal component analysis (PCA) is a technique that transforms high-dimensions data into lower-dimensions while retaining as much information as possible. Intuitively, the idea is that we can selectively keep the variables with higher variances and then forget about the variables with lower variance.  
PCA gives us our ideal set of features. It creates a set of principal components that are rank ordered by variance (the first component has higher variance than the second, the second has higher variance than the third, and so on), uncorrelated, and low in number.  

## Choosing variable selection methods
There is no set procedure which will help us select the correct variables every time. It not only depends on the type and the source of the dataset and also on the application. But here are some of the ways which we consider when choosing the variable selection technique:  
- Check the **p-values** for the coefficients and remove the variables having insignificant coefficients.  
- Before discarding variables based on the p-values you can check for data points having high **leverage** and **studentized residual**. Usually **Cook’s Distance** provides a good measure of it. If a particular data point has unusually large value of Cooks's distance, that data point can be checked as a possible influential point. It can happen that after removing the data, a particular variable which was previously significant can become insignificant.  
- **Collinearity**: Variables can be considered collinear when one variable can be well predicted from the other. The collinearity of any predictor with the others in the model can be measured with its Variance Inflation Factor (VIF). The higher the value of VIF for any variable,the greater the standard error of coefficient j and the less variable j can contribute to the regression model.
- PCA only has applications in cases where the number of features are too high- For eg: image processing, genome research, natural language processing which deal with thousands of columns. In this case one can consider using PCA and select the number of principal components to be included in the regression model based on the [elbow point method](https://sanchitamangale12.medium.com/scree-plot-733ed72c8608).