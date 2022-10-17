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
2. **Creating Data summaries** : After identifying data types one can summarizes the count, mean, standard deviation, min, and max for numeric variables. This helps you identify if there are any missing values in the numerical type variables, range of each variable etc. For each categorical variable you can find the number of unique levels.

### Cleaning the dataset  

1. **Handling Missing/Null Values** :  
Checking your data for missing values is usually a good place to start. There are multiple ways to deal with the missing/Null values and it really depends on the application and the type of the data. One can directly drop the rows containing null values, replace these values with a static value (which can be zero, mean, median etc), or perform [linear interpolation](https://en.wikipedia.org/wiki/Linear_interpolation).
2. **Spot the outliers** :  
Outliers are the observations which are significantly different than the rest of the data. There are many ways a dataset can have outliers- perhaps there was a measurement error for that sample and feature, but in many cases outliers occur naturally. It is important to spot and handle the outliers in data or this might lead to invalid predictions from machine learning models.
3. **Variable Selection** :  
Not all the variables that you have in your dataset are important for data modelling. Hence it is very important to remove redundant variables either directly or via sophisticated methods like Principle Component Analysis (PCA). 
4. **Dealing with Textual Data**: If your dataset has textual data and you want to perform anaylsis on it, then text cleaning is an extensive procedure and it includes multiple steps such as lemmatization, removing stopwords, punctuations, digits, urls, extra spaces etc.

### Analyzing the relationships between attributes  
1. **Data visualization**: It is the process of analyzing data in the form of graphs, which makes it more simpler to recognize patterns in the data. These are the following types of visualizations:

    * Univariate analysis: In this we deal with only one variable at a time. The main purpose of this is to describe any variable and find patterns in it.  
    * Bi-Variate analysis: In this we deal with two variables at a time. Analysis is done to find out the relationship among the two variables.  
    * Multi-Variate analysis: When the data involves three or more variables, it is categorized under multivariate.  

2. **Correlation Matrix** : Although this might technically fall under "Data visualization", I've listed it separately to draw attention to it. Correlation matrix is a table that shows the correlation coefficients between many variables. 

## Important methods

Below I have listed important methods which are used to implemented the strategies listed above:
1. `dplyr` package in R provides a good way to anaylse the tibble data. If any method reads in a data frame (base R) it is a good idea to convert it to a tibble using `as_tibble()` which enables us to use `tidyverse` package for plotting, reshaping and manipulating data. Following methods from dplyr package come in handy for data manipulation:
    * **filter()** : subset rows  
    * **arrange()** : reorder rows  
    * **select()** : subset columns  
    * **rename()** : rename columns  
    * **mutate()** : add a new column to tibble  
    * **transmute()** : create new variable  
    * **group_by()** : group rows by variable  
    * **summarise()** : apply functions to grouped variables  
2. Converting variables into a useful format is a crucial step. For example, if time in dataset is listed in Unix format then it would be advantageous to convert it to human readable format so that plots are more descriptive. Further if only month and year information needs to be extracted from it then `separate()` and `unite()` methods can be useful.  
It is sometimes required to convert a numerical variable into categorical variable. In this case you can check methods such as `cut()` or `qcut()`.
3. **Reshaping data** - `pivot_longer()` and `pivot_wider()` are very flexible, and can easily tidy a wide variety of non-tidy datasets.  
4. **Contingency Tables** - This is an important way for summarizing **categorical data**. `table()` function is R is used to create contingency tables. We can have:  
    * One way table: Returns the frequency of occurrence of each category in a single variable
    * Two way table: Returns a 2x2 table which accounts for frequency of occurrence of cateogries for one variable for each category of the second variable
    * Three way table: The same principal is extended for 3 categorical variables
Depending on how many categorical variables are present in your dataset, you can select which type of table to go for.
5. **Quantitative summaries** - This is used for summarizing **numerical data**. `summary()` function in R can be used to create quantitative summaries for each numerical variable. This function gives minimum, maximum, mean, median and 1st and 3rd quartiles values for the variable. Alternately, you can find summaries for numerical values 