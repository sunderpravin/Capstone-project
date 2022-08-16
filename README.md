# Capstone-project
**Fraud detection in Credit Card Transactions**

**1.Problem statement:**
  There have always been those who would develop new ways to illegally access someone's funds. Due to the boom of technology, people are more sophisticated and reliable towards online transactions. Even though the result remains same. Since all transactions are through online with the simple entry of your credit card information. When a data breach results in monetary theft eventually, the loss of client loyalty as well as the company's image. organizations, consumers, banks, and merchants are all put at risk.

**2.Approach:**
  Credit Card Fraud Detection using Machine Learning is a method that involves a Data Science team investigating data and developing a model that will deliver the best outcomes in detecting and preventing fraudulent transactions. This is accomplished by aggregating all relevant data of card users' transactions, such as the date, user zone, product category, amount, provider, client behaviour patterns, and so on. Exploration entails categorizing, aggregating, and segmenting data in order to scan millions of transactions for trends and detect fraud. It entails spotting suspicious behaviour classes, clusters, and patterns. Most of the credit card fraud detection systems are based on artificial intelligence, Meta learning and pattern matching. The Genetic algorithms are evolutionary algorithms which aim to obtain the better 
solutions in eliminating the fraud.

**3.Feature Enginnering:**
  
  **class imbalance and its treatement:**
    This problem is predominant in scenarios where anomaly detection is crucial like electricity pilferage, fraudulent transactions in banks, identification of rare diseases, etc. In this situation, the predictive model developed using conventional machine learning algorithms could be biased and inaccurate.This happens because Machine Learning Algorithms are usually designed to improve accuracy by reducing the error. Thus, they do not take into account the class distribution / proportion or balance of classes. ‘df ’ Dataframe that is application data is highly imbalanced .’defaulted population is 0.57% and non-defaulted population is 99.4%’ Total Observations = 1296675 , Fraudulent Observations = 7506, Non-fraudulent Observations = 1289169, Event Rate= 0.57% , Total columns = 22.
 
    "note: we have a seperate dataset for both train and test data"
  
  **Data Preprocessing:**
    Dropping the redundant columns from correlation matrix we can see columns with high multi collinearity ,so we can drop either one column based on vif score : 
 zip,  lat,  long,  unix time,  month,  year_dayno,  week_no
  
  **Scaling the Data:**
    Here the first step is that the data-set is split into two categories. Numerical data-set and categorical data-set. A "Power Transform" is applied feature wise to make data more Gaussian-like.Power transforms are a family of parametric, monotonic transformations that are applied to make data more Gaussian-like. This is useful for modeling issues related to heteroscedasticity (non-constant variance), or other situations where normality is desired.Currently, Power Transformer supports the Box-Cox transform and the Yeo- Johnson transform. The optimal parameter for stabilizing variance and minimizing skewness is estimated through maximum likelihood. Here the numerical variables are power transformed using yeo-johnson method.
    
  **Transformation for categorical variables:**
    The categorical data-set is now ready for a transformation. A categorical variable cannot be power-transformed. There is a method called encoding.Here we use this
categorical data encoding technique when the features are nominal(do not have any order). In one hot encoding, for each level of a categorical feature, we create a new
variable. Each category is mapped with a binary variable containing either 0 or 1. Here, 0 represents the absence, and 1 represents the presence of that category.These
newly created binary features are known as Dummy variables. The number of dummy variables depends on the levels present in the categorical variable. Dummy encoding uses N-1 features to represent N labels/categories.

  **Data Preparation:**
    After preprocessing the train data, now the data is ready for modelling and evaluation. For this purpose, the train data and test data are split into two categories. we having seperate datasets for train and train data.
    
**4.Model Building:**
  Logistic Regression is a  base classification model used to predict the probability of a categorical dependent variable . Later we used decision tree, Random Forest, Naive Bayes, Gradient Boost and XGboost classifier models .
  Since F1 score, AUC score of XGB Classifier is better than any other model and due to comparatively low variance and bias error, we consider XGB Classifier as the final model. After considering the features using feature selection, we also  create final model using XGB Classifier.
