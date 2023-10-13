# What are the drivers for Bank client term deposit subscription

The goal for this analysis is to understand the drivers of term deposit subscription for bank client


# Getting Started

### Dependencies

* Juypyter note book.
* Data Description
    *  Independent Metrics
        * 1 - age (numeric)
        * 2 - job : type of job (categorical: "admin.","blue-collar","entrepreneur","housemaid","management","retired","self-employed","services","student","technician","unemployed","unknown")
        * 3 - marital : marital status (categorical: "divorced","married","single","unknown"; note: "divorced" means divorced or widowed)
        * 4 - education (categorical: "basic.4y","basic.6y","basic.9y","high.school","illiterate","professional.course","university.degree","unknown")
        * 5 - default: has credit in default? (categorical: "no","yes","unknown")
        * 6 - housing: has housing loan? (categorical: "no","yes","unknown")
        * 7 - loan: has personal loan? (categorical: "no","yes","unknown")
        * 8 - contact: contact communication type (categorical: "cellular","telephone") 
        * 9 - month: last contact month of year (categorical: "jan", "feb", "mar", ..., "nov", "dec")
        * 10 - day_of_week: last contact day of the week (categorical: "mon","tue","wed","thu","fri")
        * 11 - duration: last contact duration, in seconds (numeric). Important note:  this attribute highly affects the output target (e.g., if duration=0 then y="no"). Yet, the duration is not known before a call is performed. Also, after the end of the call y is obviously known. Thus, this input should only be included for benchmark purposes and should be discarded if the intention is to have a realistic predictive model.
        * 12 - campaign: number of contacts performed during this campaign and for this client (numeric, includes last contact)
        * 13 - pdays: number of days that passed by after the client was last contacted from a previous campaign (numeric; 999 means client was not previously contacted)
        * 14 - previous: number of contacts performed before this campaign and for this client (numeric)
        * 15 - poutcome: outcome of the previous marketing campaign (categorical: "failure","nonexistent","success")
        * 16 - emp.var.rate: employment variation rate - quarterly indicator (numeric)
        * 17 - cons.price.idx: consumer price index - monthly indicator (numeric)     
        * 18 - cons.conf.idx: consumer confidence index - monthly indicator (numeric)     
        * 19 - euribor3m: euribor 3 month rate - daily indicator (numeric)
        * 20 - nr.employed: number of employees - quarterly indicator (numeric)

    * Output variable (desired target):
        * 21 - y - has the client subscribed a term deposit? (binary: "yes","no")



### Analysis
#### Bank - Has Client Subscribed a term deposit?
* The data contains information on the client who are a regular customer in an anonymous comercial bank. It contains the firmographic information of the client. Before dive into the analysis. There are a couple thing we would like to do for Exploration Data Anlaysis:
    * Missing Value treatment: The data contains no missing value (Null or NA). For some of the category that missing is actually already marked as "Missing"
    * Encoding: For low-cardinality feature, we used one hot encoder and ordinalencoding for high-cardinality features. This will keep the data in a clean fashion without creating excessive dummy variables
    * Normalization: For numerical variable, we normalized the data to avoid skewing the algorithm to some of the metrics with high diemsion
    * Distribution of target metric: Notice that the distribution of the target metric is extremely imbalance. Therefore, we would also need to consider tunning the parameter class_weight for algorithm that incoporate that parameter.




#### Machine Learning Model Comparison
* Various models are fitted and compare after the data was transformed. Here we have evaluated the following model and compare:
    * Logistics Regression: This is the baseline model that we fitted which took 4m51s to run which isn't bad consider the hyperparameter search space we are considering. In addition, we also applied class_weight to adjust the imbalance data set. Accuracy is 91% with 60% weight on the 'yes' class. 
    * K-Nearest-Neighbors: On the other hand for KNN, the model ran pretty fast (just under 2m). The accuracy is also competitive with Logistics model (90.7%)
    * Decision Tree: Decision tree is also showing a similar performance. In fact, a slightly better performance with 91.4% of accuracy.
    * Support Vector Machine: SVC is very computational expensive algorithm which initially took more than 1 hour to train given the parameter space we defined. Therefore, I had to trun down the parameter space to a more managable space to train. The Algorithm also performs well but SVC might not be the best one to deploy as it is more for smaller dataset with high dimensionality.

* After all, it seems like the Logistics, Decision Tree are the best one to deployment. Looking at the confusion matrix, all the models have similar performance. One thing to notice is that there may be more remedied solution for imbalance data such as under-sampling and over-sampling methodology. Given the fact that this is out of the scope, so we will not spend time right here. Another option to optimize the algorithm if we are able to train the model on the parallel machine (AWS/GCP or spark), we will be able to train more efficiently with parallel processing.



## Authors

Contributors names and contact info

ex. Mark Peng

