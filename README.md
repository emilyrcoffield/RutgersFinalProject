# Predicting Iowa Housing Prices Using Machine Learning Models
## By Kevin Menz, Lauren Gama, Myke London, Tom Shaeen, Emily Coffield
We aim to utilize various machine learning methodologies to predict the housing prices in Ames, Iowa to an acceptable accuracy. The data illustrates various home features and includes sales price and we hope to create a model that can best predict the prices that appear in the dataset.

## The Datasets
https://www.kaggle.com/emurphy/ames-iowa-housing-prices-dataset - Collection of housing data for Ames Iowa with the most recent houses built in 2010. Contains intricate housing information of individual homes.


## The Tools
The project was to create an interactive dashboard in order to answer our questions. This was done using a various set of languages and programs including:
* Python
* Pandas
* NumPy
* SciKit Learn
* XGBoost
* Seaborn
* MatPlotLib
* Tableau
* Tensorflow


## The Process
We wanted to approach this project by first figuring out what variables would make the best choices to feed into our models. We all used the same variables for the different models, and then we wanted to compare which models made the best predictions. The idea behind this is if you were to look at buying a house, what would affect the price the most and could you accurately predict the price?

The models we chose are as follows:
* Linear Regression Modelling
* Keras Neural Network
* XGBoost Model


# Analysis Process
## Part 1 - Data Prep and Variable Selection
The data was already loaded as a CSV file so we were able to pull it into Python and use Pandas to clean the data and make it suitable for analysis. We removed any empty values and made the decision to use variables with numerical values such as Square Footage, Number of Rooms, etc. We then took these variables and ran a correlation heatmap with Seaborn to see how each variable correlates with the actual price.

![Corr_HM](https://user-images.githubusercontent.com/40543168/56933022-1d50c180-6ab4-11e9-933c-207be22e74d6.png)

By looking at this we can see the variables that are correlated with Sale Price and chose the variables that most affected it.

## Part 2 - Linear Modeling
Now that the data was clean and accessible we moved to our first model. We chose to run multiple linear regressions and see how they stacked up to one another by comparing their r-squared values. See below for the results. 

![Linear Regressions Project 3](https://user-images.githubusercontent.com/40543168/56933226-e9c26700-6ab4-11e9-89e4-dc40fda3ac04.PNG)

It turns out that each linear model yielded similar results. They all hovered around a .83 r-squared value. There are subtle differences but that was the extent of it. We wanted to see what the results would be like if we ran the same models, but filtered the data only on expensive homes. 

![Expensive Regression Project 3](https://user-images.githubusercontent.com/40543168/56933355-6ce3bd00-6ab5-11e9-9f21-e2b55d2576fc.PNG)

Unfortunately this yielded an even less accurate result than the first. We believe this may have been due to a much lower sample size or the fact that we've seen a trend that the data gets more spread out the more expensive the house is.

## Part 3 - Keras Neural Network
Our next model is a Keras Neural Network. We wanted to use a Tensorflow network and chose the Keras model as it allows us to develop a regression model by passing the information through multiple epochs. This model proved to be a bit more accurate than just the straight regression model.

![Keras Neural Net Project 3](https://user-images.githubusercontent.com/40543168/56933761-255e3080-6ab7-11e9-82a4-501a9be19f64.PNG)

With a r-squared value of about .85, it proved to be a little bit more accurate than the previous model. 

## Part 4 - XGBoost Model

The final model was an XGBoost model. This model implements a gradient boosting decision tree algorithm, which is an approach where new models are created that predict the residuals of prior models, and then add them together to make the final prediction. Basically, it re-runs the model knowing the results of the previous run to get a more accurate result. This model proved to be a good choice. 

It revealed a r-squared value of .905, the highest of what we have seen so far. To show this visually, we created an interactive dashboard in Tableau to show the difference between the the predicted result and the actuals, and if they were accurate within an 20% range from the actual. 

The link for the Tableau dashboard is below
### https://public.tableau.com/profile/kevin.menz#!/vizhome/AmesIowaXGBoostModel/XGBoost?publish=yes

With this model, since it was the most accurate, we wanted to see which feature mattered the most in predicting the house price. XGBoost actually has a function for feature importantce, and you can see the results below. 

![XGBoost_Feature_Imp](https://user-images.githubusercontent.com/40543168/56934058-98b47200-6ab8-11e9-936a-c3c2cf2e9001.png)

Clearly lot area mattered the most, while having a Full Bath mattered the least out of the variables we chose. We believe this is because having a full bath is pretty much standard in every household, so having one probably affected the price the least. 

## Part 5 - Conclusion
After completing all of our models, the XGBoost model was the clear winner in predicting the house prices the most accurately. If we were to do this again, we would try to add in variables that were not just numerical and see how they affected the price. As well as see if applying this model would work for a different area, given the same criteria. 

