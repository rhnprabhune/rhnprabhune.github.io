# Exploratory Data Analysis (EDA)

## Overall goal of EDA / Things you should look for
The overall goal for the exploratory data analysis is to have a better understanding of the dataset.‘Understanding the dataset’ can refer to a number of things such as:  
* Understanding the data types of the attributes available in the dataset  
* Extracting important attributes so that redundant attributes are not carried to further analysis
* Identifying outliers, missing values 
* Understanding if there is any relationship between the attributes 
* Maximizing your insights of a dataset and minimizing potential error that may occur later in the process  
* Provide hypothesis (if required) for why the patterns occur. 

## Strategy used for EDA  
The strategies used for EDA can be broadly classified into 3 types, namely: Understanding the attributes, Cleaning the dataset and Analyzing the relationships between attributes. I have briefly described each of them below:  

### Understanding the attributes
1. **Data Types** : We first need to understand the shape of the data (Number of observations and attributes). Following that, we can move on to comprehending the data types of each variable. These are the following data types attributes can have:  
* Numerical
* Categorical
* Textual
* DateTime- These are numerical but they need to be treated differently. 
This classification helps us in selecting the visualizations we will be creating as a part of our EDA and the statistical techniques we can use with the data. Some visualizations only work with Numerical variables while some work with only categorical (R studio's [ggplot cheatsheet](https://www.rstudio.com/resources/cheatsheets/) provides a good summary for it).  
2. **Creating Data summaries** : After identifying data types one can summarizes the count, mean, standard deviation, min, and max for numeric variables. This helps you identify if there are any missing values in the numerical type variables and range of each variable. For each categorical variable you can find the number of unique levels. 
3. **Plots**: 

### Cleaning the dataset
1. **Handling Missing/Null Values** :  
Checking your data for missing values is usually a good place to start. There are multiple ways to deal with the missing/Null values and it really depends on the application and the type of the data. One can directly drop the rows containing null values, replace these values with a static value (which can be zero, mean, median etc), or perform [linear interpolation](https://en.wikipedia.org/wiki/Linear_interpolation).
2. **Spot the outliers** :  
Outliers are the observations which are significantly different than the rest of the data. There are many ways a dataset can have outliers- perhaps there was a measurement error for that sample and feature, but in many cases outliers occur naturally. It is important to spot and handle the outliers in data or this might lead to invalid predictions from machine learning models.
3. **Variable Selection** :  
Not all the variables that you have in your dataset are important for data modelling. Hence it is very important to remove redundant variables either directly or via sophisticated methods like Principle Component Analysis (PCA). 

### Analyzing the relationships between attributes


## Important methods
