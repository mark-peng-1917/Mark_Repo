### Sentiment Analysis with Machine Learning on ChatGPT Tweet comment

**Author: Mark Peng**

#### Executive summary
The purpose of the analysis is to collect and analyze the sentiment of utilizing ChatGPT. How people reacting to this type of technology that change people's day to day. The data we collected can be found at the following link: https://www.kaggle.com/datasets/charunisa/chatgpt-sentiment-analysis/

The data contains 3 type of sentiment: Good, Bad and Neutral. For our analysis, we will only looking at Good and Bad. 

Multiple model were fitted and evaluated during initial stage which includes Logistics Regression, KNN, Decision Tree and Navie Bayes (Without Hyperparameter tunning). Then the 2 of the best models were chose to compare with further hyperparameter tunning. In my analysis, due to the limited computational resource, limited parameter searching space is performed. Therefore, the best model is the logistics regression with TF-IDF,it's accuracy score is 0.965 The secondary best model would be the Navie Bayes with Word Count Vectorizier, its accuracy score is 0.927


#### Rationale
This is an crucial technology that changes people day to day, from technology sector to manufacturing, medical, insurance, banking. Imagine if AI could replace most of the non-technical job role, this will bring tremendous impact to our life. However, people might be concerned on a couple things. Such as reliability of AI, uncertainty of furture took over, etc. Therefore, analyzing the sentiment of ChatGPT is very crucial.

#### Research Question
The Reserach question is to analyze tweet on the reaction of ChatGPT

#### Data Sources
The Data source is provided by Kaggle. The tweets about chatgpt were gathered for a month and then the sentiment analysis was made using Natural Language Processing. Link to the datasource: https://www.kaggle.com/datasets/charunisa/chatgpt-sentiment-analysis/

#### Methodology
Various machine learning algorithm is used with two type of normalization and vectoriziation. The data was also manipulated and cleanse before the algorithm is applied.

#### Results
We found that Logistics regression with TF-IDF to be the best performing model

#### Next steps
Although the result of Logistics regression is great but we should also consider a wider hyper parameter search space when computation resuoce became available (or use bayesian tree search for optimal result). In addition, we should also consider ensemble modeling.


##### Contact and Further Information
Author: Mark peng
Email: yinghao89@gmail.com