
# EDA Automobile data set and simple regression

![Jupyter Notebook](https://img.shields.io/badge/Jupyter-F37626.svg?&style=for-the-badge&logo=Jupyter&logoColor=white)

![R](https://img.shields.io/badge/Python-FFD43B?style=for-the-badge&logo=python&logoColor=blue)

An exploratory Data Analysis of a dataset relevant to the automotive industry and a simple regression model
to predict the price of the cars.





# Dataset origin and breif description

The dataset was obtained from Kaggle: 
https://www.kaggle.com/datasets/toramky/automobile-dataset.

The dataset consist of data From 1985 Ward's Automotive Yearbook, contaning 3 types of entities
1. Car's characteristics
1. Insurance risk rate
1. Normalized losses in use as compared to other cars

Contains 25 different variables and 205 records.

## Summary

* Description of the type of information by type of variable and type of data
* Analysis of outliers for numeric variables
* Missing values analysis
* Interaction analysis
* Response variable analysis
* Substitution of categorical variables
* Modeling


### Description of the type of information by type of variable and type of data

* 9 categorical variables
    * 2 ordinals
    * 7 nominals
* 16 numerical variables
    * 9 discrete
    * 7 continuous 

### Analysis of outliers for numeric variables

Two methodologies werte used to detect outliers depending on the type of data distribution.

* **Normal distribution:**  Data with a value > |3| in the Z-score.
* **Asymmetric distribution:**  Data below Q1 - 1.5 IQR or above Q3 + 1.5 IQR will be considered outliers.

The varaibles *normalized-losses*, *engine-size*, *horsepower*, *peak-rpm*
*city-mpg*, *highway-mpg*, *price*, *wheel-base*, *width*, *stroke*, and *compression-ratio* 
contained at least one outlier.

### Missing values analysis

 The variable that contains the most missing values is *normalize-losses* with 20%, 
 followed by *price*, *stroke*, and *bore* with 1.95%; and *horsepower*, *num-of-doors*,
*peak-rpm* with less than 1%

### Interaction analysis

![corr](https://github.com/MaxPower14/EDA_Automobile_Dataset_Simple_Regression/blob/main/images/correlation.png?raw=true)

### Response variable analysis

![var-price](https://github.com/MaxPower14/EDA_Automobile_Dataset_Simple_Regression/blob/main/images/price-variable.png?raw=true)

### Substitution of categorical variables

* **Ordinal variables:**
Ordinal variables are those that have a specific order, in this case it is the number of doors (num-of-doors) and the number of cylinders (num-of-cylinders). This substitution will simply consist of converting text to its corresponding number.

* **Nominal variables:**
They are those variables that do not have a specific order, which are categories without a specific hierarchy. In this case they are: make, fuel-type, aspiration, body-style, drive-wheels, engine-location, engine-type, fuel-system. For this type of variables a frequency encoder will be used. This consists of replacing the category with its number of repetitions for that column.

![cat-corr](https://github.com/MaxPower14/EDA_Automobile_Dataset_Simple_Regression/blob/main/images/cat-correlation.png?raw=true)


### Modeling

A Random Forest Regressor model was applied to predict the price variable. 
The performance was measured calculating 3 different metrics:
* Mean Absolute Error
* Mean Absolute Percentage Error
* Correlation