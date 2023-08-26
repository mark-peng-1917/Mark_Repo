# what are the driver for used card

The goal for this analysis is to understand the driver of the used car in the market. The data capture US used car trading price as well as the feature and ocndition of the vehicle


# Getting Started

### Dependencies

* Juypyter note book.
* Data Description
    * 1. User attributes
        *  ID:unique identifier
        *  Region: US Region
        *  price: Price of the car (Target)
        *  model: Model of the car
        *  manufacturer: manufacturer of the car
        *  condition: condition of the car
        *  cylinders: cylinders
        *  fuel: fuel that consumed
        *  odometer: current odometer
        *  title_status: title status
        *  transmission: transmission of the car
        *  VIN: VIN number (unique identifier)
        *  drive: FWD, RWD, AWD
        *  size: size of the car
        *  type: type of the car
        *  state: state of the car
        

    3. Target attribute
        - Price of the veichle


### Analysis
#### Coupon acceptance for Bar
* The data contains a good amount of missing data across all different columns except for VIN and id (which we only need to keep one of the two). Before we perform any analysis, we applied the following treatmnet using Pipeline:
    * Missing Value treatment: Mean was applied for odometer while most_frequent was applied on year. mean of year does not really make tons of sense. For categorical features, we distinguish them into two groups: low-cardinality and high-cardinality. For both, we impute using the constant value "missing"
    * Encoding: For low-cardinality feature, we used one hot encoder and ordinalencoding for high-cardinality features.

* We also applied a correlation analysis to the dataset to check correlation between the target and the features. Unfortunatley, there is no obvious linear relationship between the target and the feature.



#### Machine Learning Model Comparison
* Various models are fitted and compare after the data was transformed. Here we have evaluated the following model and compare:
    * Simple Linear regression: this would be our baseline model with no polynomial term. the R2 for test is -.00628 which is very poor in terms of predictivity. We also tried to remove the high cardinality metrics but the result are the same.
    * Linear regression with polynomial terms (2): this is the expansion of the previous model and the performances increase to -.175 for R2 which is a huge jump. This explain why correlation is low and it seems like the we are observing some non-linear relationship between feature and target.
    * Lasso: the polynomial term for Lasso took a long time so we dropped the polynomial terms out. However, R2 is also poor
    * Ridge: Ridge with poly terms (2) shows a very similar result with the linear model with poly term(2)
    * Ridge with f_regression best K set: the performance is also poor

* After all, it seems like the simple linear regression with polynomial terms is the best performer. Therefore, we also evaluated the feature importance chart based on the model. it looks like condition, fuel and cylinders are the most predictive features.



## Authors

Contributors names and contact info

ex. Mark Peng

