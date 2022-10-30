# Variable Selection for Regression

## Need for variable selection
When creating a data model, the selection of the variables is extremely important to improve the accuracy of the model. However while creating the model one doesn’t know the variables which should be included and those that should be discarded. The response variable y could depend on a number of Independent variables x1,x2,x3,….xp. These number of variables are often too large to be considered in a statistical model.  
Other than that a huge number of variables could lead to addition of unnecessary noise and lead to **over-fitting** (Over-fitting is when the model describes the random errors and noise instead of just describing the underlying relationship). One must also consider that there is cost associated to measuring the predictors and hence variable selection would save the cost if the model is used for prediction.

## Methods for variable selection  
### Selection Procedures  

1. **Forward Selection** : It is A stepwise variable selection procedure in which variables are sequentially entered into the model. It starts with no variables in the model. For each variable not in the model, the extent of the variable’s contribution is calculated, and the largest contributing variable is selected for entry into the equation. The variable is entered into the equation only if it satisfies a specified criterion for entry. This process is repeated until no variables meet the entry criterion.

2. **Backward Elimination**: It is the opposite of Forward selection in which the model initially has all the variables included and then they are sequentially removed. The variable with the smallest partial correlation with the dependent variable or in other words whose contribution is the least is first considered for removal. If the criteria for elimination is met then the variable is removed. This process is also repeated until all the insignificant variables are removed.

3. **Stepwise**: Stepwise is a combination of forward selection and backward Elimination except that the variables added at a step don’t necessarily stay Stepwise search checks going both backwards and forwards at every step. It considers the addition of any variable not currently in the model, as well as the removal of any variable currently in the model.