# Project 2 Review

I recently completed [Project 2](https://namangoel05.github.io/ST558_Project2_2D/) as a part of my curriculum for **ST 558: Data Science for Statisticians**.

## Purpose of the project
The main goal of the project was to use github pages to develop a vignette that demonstrated how to query, parse, and return well-structured data in the form of a data frame from REST API Endpoints using user-defined functions. I conducted some exploratory data analysis after acquiring the data in order to draw some insights from it. Box plots, contingency tables, summary tables, histograms, etc. were included in this.  
The API that I selected for this project is [Financial Market Data](https://polygon.io/docs/stocks). The Polygon.io Stocks API provides REST endpoints that let you query the latest market data from all US stock exchanges.

## Learnings and Challenges
I had a theoretical understanding of what APIs are and how they operate prior to working on this project, but I had never had the opportunity to put it to use. I had the ideal opportunity to work with REST API endpoints on this project, which was extremely interesting. Along the way, I had the opportunity to work with the R packages 'httr' and 'jsonlite'.

### Learnings  
1. I gained hands-on experience to use an API endpoint to query data through this project. Additionally, I was able to analyze the data provided on the API information website.   
2. I had the opportunity to spend a significant amount of time working on the `ggplot2` R package, which was used to produce different kinds of plots for data analysis. I also learned how to navigate through the [ggplot cheatsheet](https://www.rstudio.com/resources/cheatsheets/) offered by R studio, which I feel is a crucial component of plotting in R because it is impossible to memorize all the syntax. The cheat sheet aids in getting information very quickly.  
3. I developed the functions to query data from API Endpoints once we determined which endpoints to fetch it from. I was able to write the functions quite well thanks to the knowledge I obtained from working on Project 1 of this course.   

### Challenges
1. One of the first challenges I encountered in this project was querying the API Endpoint and subsequently understanding and parsing the fetched data. Although this was discussed in class, which was helpful, I first attempted using the [Food API](https://spoonacular.com/food-api/docs) before choosing the Financial Market Data API. It was quite difficult to parse the data into a structured manner that was returned by some of the endpoints in Food Data. Eventually I decided to go with Financial data as I was able to figure out how to parse the data returned.  
2. One of the timestamp returned by the API was in Unix msec format. I tried a bunch of R packages to convert it to human readable datetime format but was unable to do it. Probably I need to manipulate the data first that then use the existing R packages.  
3. Polygon.io provided some endpoints which were Market Data Endpoints and some were Reference Data Endpoints. Often to make the plots more descriptive, I was required to combine information from multiple endpoints. I struggled with this part initially, but I managed to get it done. However I feel that there might be more efficient approaches of doing it.  

## What I would do differently
For this project, my teammate and I had to use github to commit our code changes. I initially believed that since this project was not too large, we could both commit our changes to the main branch at once. But I believe that working on our individual feature branches, making PRs, and using a more formal approach would have been better for us both. Therefore, I would definitely consider that in the upcoming group projects.