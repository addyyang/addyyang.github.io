# CS4641 Project Proposal: Flight Delay Predictor'
### Introduction/Background
There exist sites, like https://wingman.wtf/ and https://www.knowdelay.com/index.html that predict flight delays but are often too inaccurate to fully rely on. Scholarly articles that detail the use of ML in predicting flight delays generally focus on a single airport or airline, and use regression models like decision trees \[1\]. 
We plan on approaching this problem in several ways, with a more expansive dataset that details predicted vs. actual departure times of previous flights, airlines, # of passengers, weather, airport flight volume, and aircraft age and size. We also plan to analyze this problem at multiple scales, using regression, clustering, and classification techniques to predict the length of flight delays, category of delay (i.e. <30 mins, 30-60 mins, etc.), and simply existence of delay.

### Problem Definition
Airline delays are a frustration for passengers, and because of the few resources available to accurately forecast potential delays, through this project, we aim to help travelers determine when delays are most likely to occur, and airports and airlines provide more reliable information about their operations.

### Methods
#### Data Preprocessing Methods
+ **Data cleaning** will ensured that our data is free of outliers or incorrect/null data. We'll use the Pandas library, including dropna() and drop_duplicates(), to do this effectively. We also deleted outlier datapoints with delays over 500 minutes. For regressors, we changed datapoints with "negative" delays (the plane arrived early to the destination) to zero. 
+ We used **feature transformation** to adjust data to best fit the strengths, weaknesses, and biases of our model/dataset. For example, we used the log transformation technique from scikit-learn to normalize right-skewed data.
+ We used **dimensionality reduction** to prevent overfitting while still considering the impact of eliminating features on the accuracy of our model \[2\].

#### ML Algorithms/Models (supervised only)
+ Our initial approach made use of **linear regression** to attempt to predict the number of minutes a flight will be delayed. We chose this because we wanted to attempt a regression task, and thought linear regression would be a simple and good introduction to creating models and experimening with optimization and using the libraries available.
+ For our second approach, we attempted to use a **random forest** model to classify flights into buckets. In general, we thought random forests would be a suitable approach because of their [citation]
+ For our final approach, we used **gradient-boosting** to implement another regression method. We chose this model because of its power to handle non-linear relationships, which was the main problem with our first model. Gradient-boosted regressors are also able to provide insights into feature importance, which is helpful for our dataset due to the large amount of features we have [citation]. Finally, we chose this model because of its robustness to overfitting [https://cdn.techscience.cn/uploads/attached/file/20210520/20210520060421_37669.pdf], which was a prominent problem that we noticed in our previous two models.

### Potential Results and Discussion
+ For our linear regression model, two main trials were run: one with all features present, and the other with just 7. The 7 most important feature were selected by performing forward feature selection on the training data. The regression model was then fit to each of the two sets of training data, then used to predict delays for the remaining 20% of the data (test set). The initial 80% of the data was the training set. Scikit-learn was the library used for this implementation.
### 3+ Quantitative Metrics
+ For a linear regression model, **mean-squared error (MSE)** will effectively measure our accuracy while incentivizing few large errors (i.e. predicting no delay when in fact a 24-hour delay occurred).
+ We will also consider **mean absolute deviation (MAD)**. However, we will prioritize minimizing MSE, which is more punitive of exceptionally large residuals than MAD, thereby creating more helpful predictions.
+ For our clustering and classification approaches, we will consider **Rand Score** and **F1 score** to evaluate accuracy.
  
### Project Goals
+ Create a regression model that accurately predicts length of flight delays -> ex. Adjusted R2 > ~0.9 (dependent on MSE)
+ Create an accurate classification model that predicts existence of flight delays -> ex. F1 score > ~ 0.75

### Expected Results
+ Identify the biggest reasons for flight delays across our datasets.
+ Predict flight delays with accuracy that will help travelers.
+ Determine whether length or existence of a delay is easier to accurately predict.

### References
\[1\] H. Khaksar and A. Sheikholeslami, “Airline delay prediction by machine learning algorithms,” Scientia Iranica, vol. 0, no. 0, pp. 0–0, Dec. 2017. doi:10.24200/sci.2017.20020 

\[2\] H. S. Obaid, S. A. Dheyab and S. S. Sabry, "The Impact of Data Pre-Processing Techniques and Dimensionality Reduction on the Accuracy of Machine Learning," 2019 9th Annual Information Technology, Electromechanical Engineering and Microelectronics Conference (IEMECON), Jaipur, India, 2019, pp. 279-283, doi: 10.1109/IEMECONX.2019.8877011.

\[3\] S. Manna, S. Biswas, R. Kundu, S. Rakshit, P. Gupta and S. Barman, "A statistical approach to predict flight delay using gradient boosted decision tree," 2017 International Conference on Computational Intelligence in Data Science(ICCIDS), Chennai, India, 2017, pp. 1-5, doi: 10.1109/ICCIDS.2017.8272656.

## [Gantt Chart](https://docs.google.com/spreadsheets/d/1DOtCJ0PgNM5uBerABgMfCDr11GxqrQK8Jsl495TC0UA/edit?usp=sharing)

## Team Contribution Table
| Name  | Proposal Contributions |
| ------------- | ------------- |
| Addy Yang  | Report sections 1, 3, and 5, creating Github.io page, Gantt chart  |
| Rohan Bhagat  | Report sections 1-4, Video Presentation  |
| Dhruv Shrivastava  | Created Google Slides Presentation, Report Section 4  |
| Aidan Pratt  | Project Idea, Video Presentation, Google Slides |
| Teddy Feldman  | Report Sections 1-5 |
