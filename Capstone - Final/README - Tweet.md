### Sentiment Analysis with Machine Learning on ChatGPT Tweet comment

**Author: Mark Peng**

#### Executive summary
The purpose of the analysis is to collect and analyze the sentiment of utilizing ChatGPT. How people reacting to this type of technology that change people's day to day. The data we collected can be found at the following link: https://www.kaggle.com/datasets/charunisa/chatgpt-sentiment-analysis/

The data contains 3 type of sentiment: Good, Bad and Neutral. For our analysis, we will only looking at Good and Bad. 

Multiple models were fitted and evaluated during initial stage which includes Logistics Regression, KNN, Decision Tree and Navie Bayes (Without Hyperparameter tunning), Random Forest and XGBoost Classifier. Then the 2 of the best models were chose to compare with further hyperparameter tunning. In my analysis, due to the limited computational resource, limited parameter searching space is performed. Therefore, the best model is the logistics regression with TF-IDF,its accuracy score is 0.966 The secondary best model would be the Navie Bayes with Word Count Vectorizier, its accuracy score is 0.922 followed by XGBoost Classifier with Word Count vectorizier (accuracy score of .912). Hyper parameter tunning might not be really helpful in our case due to the fact of computational power is limited and the tunned model showed a little improvement (decline in accuracy for logistics regression) compare to the initialed models.


#### Rationale
This is an crucial technology that changes people day to day, from technology sector to manufacturing, medical, insurance, banking. Imagine if AI could replace most of the non-technical job role, this will bring tremendous impact to our life. However, people might be concerned on a couple things. Such as reliability of AI, uncertainty of furture took over, etc. Therefore, analyzing the sentiment of ChatGPT is very crucial.

#### Research Question
The Reserach question is to analyze tweet on the reaction of ChatGPT

#### Data Sources
The Data source is provided by Kaggle. The tweets about chatgpt were gathered for a month and then the sentiment analysis was made using Natural Language Processing. Link to the datasource: https://www.kaggle.com/datasets/charunisa/chatgpt-sentiment-analysis/

#### Methodology
Various machine learning algorithm is used with two type of normalization and vectoriziation. The data was also manipulated and cleanse before the algorithm is applied. Type of manipulation includes:
	* Cleaning the content of the tweet by removing website which start with "https://"
	* Removing non-alphanumber that contains special character or emoji

We also explored word cloude to visualize what is matter the most to people. Lastly, different model is fitted and the best 2 models is chose to further tuned its parameters

#### Results
In the initial word cloud, we see people mentioned ChatGPT and OpenAI alot but this is not very obvious what other topics that other people are discussing. Therefore, a second iteration with ChatGPT and OpenAI are added. Now, we can see that people mentioned about Google, AI, futher, good, human, better, code. Overall, the attitude of ChatGPT is mostly positive with majority of the people is thinking this is a revoluationary change that we (as human) can advanced with AI and the future is very likely.

For modeling part, 11 models are fitted and compared. Logistics with word count is the best performning model (with accuracy of 0.966), followed by Mutinomial Navie Bayes (accuarcy of 0.922) and XGBoost (accurarcy of 0.912). During the hyper-parameter tunning section, logistics regression lose its accurarcy due to the limited parameter space we are searching. On the other hand, XGBoost did gained a non-noticeable improvement. 

Overall, the top 3 models are very good in terms of predicting Bad vs Good sentiment given its accurarcy is great than 90%. 

#### Next steps
Although the result of Logistics regression is great but we should also consider a wider hyper parameter search space when computation resuoce became available (or use bayesian tree search for optimal result). In addition, we should also consider using cloud computing which we could potential leverage spark or parallel computating to offload some of the computating overhead. 


##### Contact and Further Information
Author: Mark peng
Email: yinghao89@gmail.com