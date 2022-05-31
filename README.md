## Problem Statement

Ultimately, the goal of a real estate investor is to generate a profit on a healthy investment. This project will use real estate data in Ames, Iowa to create an 
1. **accurate** machine learning model to predict housing prices based on certain factors, and 
2. use the results of that model to determine the factors that have the largest impact on housing prices.

This project aims to answer the problem question: As qualities of a house change, how does home price change?

## Background:
The success of the model and project are going to be determined by Root Mean Squared Error (RMSE) and comparing it to the Null RMSE. The Null RMSE is calculated by comparing the sale price values with the mean. If our model RMSE is higher than the Null RMSE, then our model is not better than simply using a mean housing price to generate predictions. The RMSE will be in the same units as the y variable (Sale Price). This project will be successful if the model created is lower than the Null RMSE. [Root Mean Squared Error](https://en.wikipedia.org/wiki/Root-mean-square_deviation).

## Datasets used:

1. train.csv: Contains data pertaining to features that properties have in Ames, Iowa, and the prices of those properties
2. test.csv: Same as train.csv, but used only to test a final accuracy score
3. train_clean.csv: Contains only the housing features used in the final model, with outliers removed.

## Outside Research

I used a research study in 2017 to help me narrow down and identify certain housing variables to consider using in my final model. This study found that the strongest variables that affect housing prices are 1) condition of the home, 2) concept of the home, and 3) neighborhood or surroundings of the home. [(Alfiyatin et al., 2017)](https://www.researchgate.net/profile/Wayan-Mahmudy-2/publication/320801620_Modeling_House_Price_Prediction_using_Regression_Analysis_and_Particle_Swarm_Optimization_Case_Study_Malang_East_Java_Indonesia/links/5a0fdbc4458515cc5aa6a91f/Modeling-House-Price-Prediction-using-Regression-Analysis-and-Particle-Swarm-Optimization-Case-Study-Malang-East-Java-Indonesia.pdf).

## Data Dictionary

|Feature|Type|Dataset|Description|
|---|---|---|---|
|**id**|*int*|Training Data Cleaned|Property Identification Number|
|**home_quality**|*int*|Training Data Cleaned|Rating of home quality, on a scale of 1-10|
|**home_sqft**|*int*|Training Data Cleaned|Total indoor square footage of each property, calculated from the original data|
|**home_age**|*int*|Training Data Cleaned|Age of the home between initial construction and year sold, calculated from the original data|
|**yr_remod**|*int*|Training Data Cleaned|Most recent year remodeled. If there was no remodel, this value is the date of initial construction|
|**full_bath**|*int*|Training Data Cleaned|Number of full baths in the property|
|**masonry_veneer_area**|*int*|Training Data Cleaned|Square footage of aesthetic additions to the outside of the property (e.g. stone, brick, etc.)|
|**total_rooms_above_ground**|*int*|Training Data Cleaned|Number of rooms excluding the basement of a property|
|**neighborhood**|*object*|Training Data Cleaned|The neighborhood in which a property is located|
|**home_type**|*object*|Training Data Cleaned|The type, style, or class of home (e.g. Duplex)|
|**sale_price**|*int*|Training Data Cleaned|Price of the home|

**Visual assets, graphs, and charts can be found in the assets folder or the presentation file in this repo.**

## Conclusions and Recommendations

The goal of this project is to create a
1) **accurate** machine learning model to predict housing prices based on certain factors, and 
2) use the results of that model to determine the factors that have the largest impact on housing prices.

The variables that have the strongest effect on home price as identified by our model include:
1. home square footage
2. home quality
3. neighborhood
4. home type

For every 1 unit change in home square footage, home price increases by 17%.
For every 1 unit change in home quality rating, home price increase by 10%.

This model is designed to increase potential profit from real estate investment if used in conjunction with investment strategy. This model may also help investors detect inefficiencies in house prices and find undervalued homes based on the features that the model uses to calculate home price. New construction investors can also use this information to confirm if certain properties will retain/gain value or not based on the features that have strong effects on home price.

This model can account for approximately 84% of variance in new, unseen data, and our RMSE on unseen data is 23638. This means that there is an element of risk - the positive and negative range of potential error that the model could predict is up to $23,638 when our model is trying to predict home price. At a higher scale, and especially in today's housing market, this error is minimal, especially beyond the $400,000 range. Also, our model cannot account for 16% of variance in the data. Comparing this to the null RMSE (65897), using our model to predict home price or interpret which variables have a measured effect is going to be much more effective than simply guessing by using the mean home price.
