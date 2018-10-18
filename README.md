# wine
Analysis and modelling of a Kaggle wine dataset

The Jupyter Notebook found in this repository contains an exercise in analyzing and modelling data based on the Kaggle _Wine Reviews_ dataset, which can be found [here](https://www.kaggle.com/zynicide/wine-reviews). The dataset contains around 130,000 reviews.


### Dependencies
 
_wine.ipynb_ was implemented in Python 3.6.6 and Jupyter Notebook version 5.6.0 running Conda version 4.5.11.

Libraries used:

* numpy
* pandas
* matplotlib
* seaborn
* sklearn


### Summary of the analysis and modelling

The analysis part tries to answer the following questions:

1. Which country and region produces the best wine (based on points on the 0-100 scale wine rating)?
2. What is the relationship between points and price?
3. What is the most overpriced wine in the dataset, i.e. the wine with the highest price relative to other wines with the same rating?
3. What is the "best value for money" wine in the dataset, i.e. the wine with the lowest price relative to other wines with the same rating?

The questions above are answered by performing straightforward operations on a pandas DataFrame.

The modelling part is an attempt to predict the rating based on other features (Country, Year, Province, Region and Price). Two different Scikit Learn classifier models are used (Random Forest and a Neural Network), and for each a Grid Search is performed in order to improve the models over the defaults by optimizing their parameters. 

With the default parameters the Random Forest model achieves a fairly high accuracy of 88% on the training data, but no more than 59% on the test data. A clear case of overfitting.

The Neural Network gives a lower accuracy of 65% on the training data, and 63% on the test data. Less overfitting, but still pretty far from a desired result.

The grid searches did not manage to produce models that scored better than the ones using default parameters. A more comprehensive parameter search was not attempted, as each run took more than an hour.

The low accuracy achieved with either model suggests either that the models are poor, that the dataset is too small, or that wine ratings are so subjective that there is no relationship between the chosen features and the rating!

One final attempt is made at improving the accuracy by including the _taster_name_ in the dataset. Unfortunately this data is missing for a lot of reviews, resulting in an even smaller dataset. In any case the inclusion of the this variable did not have any effect on the accuracy of the models.

