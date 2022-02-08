# Housing_Prices_Regression

***Ask a home buyer to describe their dream house, and they probably won’t begin with the height of the basement ceiling or the proximity to an east-west railroad. But this  dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.
We are trying to answer the question as to what features affects the price of house ?***

I followed the following steps to answer this question : 

1.Data exploration\
2.Data cleaning\
3.Model building

### Overview

There are 1460 instances of training data and 1460 of test data. Total number of attributes equals 81, of which 36 is quantitative, 43 categorical + Id and SalePrice.

Quantitative: 1stFlrSF, 2ndFlrSF, 3SsnPorch, BedroomAbvGr, BsmtFinSF1, BsmtFinSF2, BsmtFullBath, BsmtHalfBath, BsmtUnfSF, EnclosedPorch, Fireplaces, FullBath, GarageArea, GarageCars, GarageYrBlt, GrLivArea, HalfBath, KitchenAbvGr, LotArea, LotFrontage, LowQualFinSF, MSSubClass, MasVnrArea, MiscVal, MoSold, OpenPorchSF, OverallCond, OverallQual, PoolArea, ScreenPorch, TotRmsAbvGrd, TotalBsmtSF, WoodDeckSF, YearBuilt, YearRemodAdd, YrSold

Qualitative: Alley, BldgType, BsmtCond, BsmtExposure, BsmtFinType1, BsmtFinType2, BsmtQual, CentralAir, Condition1, Condition2, Electrical, ExterCond, ExterQual, Exterior1st, Exterior2nd, Fence, FireplaceQu, Foundation, Functional, GarageCond, GarageFinish, GarageQual, GarageType, Heating, HeatingQC, HouseStyle, KitchenQual, LandContour, LandSlope, LotConfig, LotShape, MSZoning, MasVnrType, MiscFeature, Neighborhood, PavedDrive, PoolQC, RoofMatl, RoofStyle, SaleCondition, SaleType, Street, Utilities,



### Data Exploration or EDA (Exploratory Data Analysis)

Exploratory Data Analysis (EDA) is the crucial process of using summary statistics and graphical representations to perform preliminary investigations on data in order to uncover patterns, detect anomalies, test hypotheses, and verify assumptions.

On doing EDA we uncovered the following :

1.Features like PoolQc , MiscFeature and Alley have more than 90% missing values. Such columns are not  useful in predicting the model. We  remove features which have over 40% missing values.\
2.There are many strong correlations between variables. Garages seem to be built same year as houses, basements have generally same area as first floor which is pretty obvious. Garage area is strongly correlated with number of cars. Neighborhood is correlated with lots of other variables and this confirms the idea that houses in same region share same characteristics. Dwelling type is negatively correlated with kitchen above grade square feet.

### Feature Engineering

Importance : We need to build new features based on the exisiting information to reduce the sparsity in the data and feeding only the relevant data to the model.The goal is to simplify and speed up data transformations while also enhancing model accuracy.

1.We made a new feature isRemodeledRecent to check whether the house was remodeled recently as it will help in figuring out if remodeling he house have any affect on the prices.\
2.Similarly we create a feature new_house_status to check whether the house was recently.\
3.Features to check average number of rooms in houses , garage and bathrooms above ground were made to make the features more relevant as such features will help greater role in determing the price of house.\
4.Location of house is always an important factor in determing the price of house so we made features for nearby transits and services of the house\
5.Feature related to Area of the house , porch area and quality of house were made as these are valuable features and will help in algorthim accuracy\
6.We transform numerical columns to binary columns to speed up training of model and improving the accuracy.

***IMPUTING MISSING VALUES***

Importance : The benefit of the  imputation is that in addition to restoring the natural variability of the missing values, it incorporates the uncertainty due to the missing data, which results in a valid statistical inference. Restoring the natural variability of the missing data can be achieved by replacing the missing data with the imputed values which are predicted using the variables correlated with the missing data. Incorporating uncertainty is made by producing different versions of the missing data and observing the variability between the imputed data sets.

We used KNN imputer to impute the missing values.This imputer utilizes the k-Nearest Neighbors method to replace the missing values in the datasets with the mean value from the parameter ‘n_neighbors’ nearest neighbors found in the training set. By default, it uses a Euclidean distance metric to impute the missing values.
