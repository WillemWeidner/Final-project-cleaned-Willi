Project title: US stores sales prediction

Research Questions: 

    1. How do geographical location, market factors, and weather conditions influence sales performance in the given context?

    2. How to effectively predict sales values for US stores using a combination of sales data, store information, product information, accounting                     information, and as features?


How to answer the Research questions: By conducting an exploratory data analysis (Research Question 1) and building a predicitve model (Research question 2) 


Objectives: (Data Science End to End Project)

    * Data collection: Extract Data from APIs and combine them with the data from my main sales dataset. 

    * Data cleaning and wrangling

    * Exploratory data analysis (answer 1. Research question)

    * Feature engineering, preprocessing

    * Model selection, evaluation and data visualization (answer second Research question)


Motivation:

    * A better prediction can help companies to improve their sales performance and set more accurate sales targets. 


Code style/ Tech/framework used

    * Using Pandas, matplotlib, seaborn, for visualisation.


API Reference/ Source for original data

    * Source for original data: US Stores Sales
        Link: https://www.kaggle.com/datasets/dsfelix/us-stores-sales/data

    * API Reference 1: https://opencagedata.com/api
    * API Reference 2: https://open-meteo.com/en/docs/historical-weather-api


Presentation:
    * Link: https://docs.google.com/presentation/d/1cSZat9OrjxjF6W11ZFHSv4khDlDHdjNkpXjjkNWJqBo/edit?usp=sharing


Conclusion/ Findings of the project:

* 1.1 The first part of the first research question: How do weather conditions influence sales performance

        * A comparison of the weather data line graphs for the locations with our sales line graph looks an on first sight like there could be a possible                 correlation between sunshine duration and sales if you only look at the year 2010 and would not have the data for 2011.

        * Sales plunge between mid-June and the end of November, remaining at a relatively low level until December, and then peaking in January before                   declining again.

        * Sunshine duration for our locations also plunges from July 2010 to January 2011 and starts to rise again in January. A similar pattern is observed              for daylight duration.

        * However, when examining 2011, we note that sales values are much less volatile. Daylight duration and Sunshine duration varie over time, but sales              does not necessarily follow the same pattern. They do not appear to be a significant factor in determining sales and have a low correlation to the              target sales.   

        * This also chekcs out with sales not having a clear seasonal pattern. 

        * The other weather data has also no apparent correlation. 


* 1.2 The second part of the first research question: How do geographical location and market factors influence sales performance

        * Looking at the geographical data we can see the following:
        * Based on the scatter plot of sales by area code, there is no clear correlation between area code and sales. The data points are scattered randomly,             with no discernible pattern. This suggests that sales are not significantly influenced by area code.
        * The box and whisker plot of sales by market does not reveal a clear correlation either. The boxes for each market overlap significantly, indicating             that the distributions of sales values are similar across markets. Additionally, the median sales values for each market are relatively close                   together.
        * In summary, while there are some indications of correlation between sales and weather conditions for 2010, these findings are not robust enough to              establish a definitive link. Similarly, there is no clear correlation between sales and geographical location or market factors.


2. How to effectively predict sales values for US stores using a combination of sales data, store information, product information, accounting information as features?

    Answer:

    * I evaluated three models on my data. 
    * DecisionTreeRegressor was my best performing model, but also overfitting
    * Cross-validation to assess the performance of the model further, where DecisionTreeRegressor had the highest score together with one of my other models
        # since DecisionTreeRegressor was clearly overfitting in the first evaluation I proceeded with this model, since I wanted to treat the overfitting
    * Feature Selection
        * Variance threshold to reduce the number of features in a dataset by removing features with low variance (ended up removing 2 out of 
        * which are considered to be less relevant or informative. This can be useful for reducing the amount of noise in the data and improving the                      performance of machine learning models, especially when they are prone to overfitting.
        * R2 score did not change significantly
    * I optimization of parameters for my chosen model DecisionTreeRegressor
        * DecisionTreeRegressor is not overfitting in such a extreme way anymre
        * Test and train score still significant difference but train less overfitted
    * Then I conducted a Hyperparameter search
    * Used the best Hyperparameters from Grid search to optimize the model
    * Used the best Hyperparameters from Grid search to optimize the model
            * And got another performance improvement on test data data R2 score: 0.96 %
