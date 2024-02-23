# CS4641 Project Proposal: Flight Delay Predictor

### Introduction/Background
There are existing sites, like https://wingman.wtf/ and https://www.knowdelay.com/index.html that seemingly provide a similar service, but produce an errors when attempting to search for flights. Scholarly articles that detail how machine learning could aid in predicting flight delays generally focus on a single airport or airline, and used regression models like decision trees \[1\]. 
We plan on using datasets containing data on predicted vs. actual departure times of previous flights, which airline it's operated by, the number of people on each flight (including number of seats oversold and passengers on standby), weather (eg. temperature, precipitation, fog), flight volumes at each airport, and aircraft type (eg. age, size).

### Problem Definition
Airline delays are a frustration for passengers, and there are few resources available to predict which routes, airlines, and/or airports commonly have the most delays. Our motivation is that travellers should have the knowledge of when delays are most likely to occur, so they can plan their travels accordingly when timing is tight. Such a resource can also be beneficial for airports to optimize their operations, and for airlines to provide more reliable information and improve customer satisfaction.

### Methods
#### Data Preprocessing Methods
+ **Data cleaning** will ensure that our data is free of outliers or incorrect data: a necessary precaution given we will be sourcing our data from the internet.
+ We will use **feature transformation** to place higher emphasis on features that likely have a greater impact on delays, like precipitation.
+ We will use **dimensionality reduction** to ensure that the size of our dataset is not too large to work with, but conisdering the impact of eliminating features on the accuracy of our model \[2\].
#### ML Algorithms/Models (supervised only)
+ **Gradient-boosted decision trees** are a popular and effective model for flight delay predictors, and are suitable for our project because of their high accuracy, and ability to provide useful insight on which features contribute heaviest to flight delays \[3\]
+ If predicting a continuous target variable proves to be too difficult, and/or we decide we want to predict the delay time in intervals, then **hierarchical clustering** would be a good start, to give us an idea of how many buckets are ideal, since we are not sure how small/large the intervals will be for a good balance of accuracy and correctness (eg. 0-10 min delay, or 0-30 min delay?).

### (Potential) Results and Discussion
### 3+ Quantitative Metrics
+ If we persist with a linear regression model, **mean-squared error (MSE)** is a simple but effective way of calculating accuracy. Since MSE heavily penalizes incorrectness, it will be challenging to achieve a low MSE value.
+ 
###

### References
\[1\] H. Khaksar and A. Sheikholeslami, “Airline delay prediction by machine learning algorithms,” Scientia Iranica, vol. 0, no. 0, pp. 0–0, Dec. 2017. doi:10.24200/sci.2017.20020 

\[2\] H. S. Obaid, S. A. Dheyab and S. S. Sabry, "The Impact of Data Pre-Processing Techniques and Dimensionality Reduction on the Accuracy of Machine Learning," 2019 9th Annual Information Technology, Electromechanical Engineering and Microelectronics Conference (IEMECON), Jaipur, India, 2019, pp. 279-283, doi: 10.1109/IEMECONX.2019.8877011.

\[3\] S. Manna, S. Biswas, R. Kundu, S. Rakshit, P. Gupta and S. Barman, "A statistical approach to predict flight delay using gradient boosted decision tree," 2017 International Conference on Computational Intelligence in Data Science(ICCIDS), Chennai, India, 2017, pp. 1-5, doi: 10.1109/ICCIDS.2017.8272656.

## [Gantt Chart](https://docs.google.com/spreadsheets/d/1DOtCJ0PgNM5uBerABgMfCDr11GxqrQK8Jsl495TC0UA/edit?usp=sharing)

## Team Contribution Table
| Name  | Proposal Contributions |
| ------------- | ------------- |
| Addy Yang  | Report sections 1, 3, and 5, creating Github.io page, Gantt chart  |
| Rohan Bhagat  | Content Cell  |
| Dhruv Shrivastava  | Content Cell  |
| Aidan Pratt  | Content Cell  |
| Teddy Feldman  | Content Cell  |
