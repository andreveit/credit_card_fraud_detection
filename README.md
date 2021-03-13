   **Author:** Andre Veit

   **LinkedIn:** https://www.linkedin.com/in/andreveit/

   **E-mail:** andrev.veit@gmail.com

# CREDIT CARD FRAUD DECTECTION
## Classification of Imbalanced Data and Anomaly Detection

![creditcardimg.jpg](https://github.com/andreveit/credit_card_fraud_detection/blob/main/creditcardimg.jpg?raw=true)

# **About this notebook**


Fraud is not something new, in a matter of fact, according to Your Money website, the first fraud register happened back in 300 BC. Now a days, in a world where the internet and digitalization is increasing at an unbelievable rate, millions of transactions and other operations are realized every day through the network. That means many opportunities for fraudsters. 

Fortunately, there are relatively few. Unfortunately... this fact makes extremely hard to catch them. 

The objective of this notebook is to explore a few methods to deal with anomaly detection and highly imbalanced data sets.

<br>
<br>

### **Overview:**

1. Data Exploration and Preparation
2. Unsupervised Learning - Anomaly Detection
>2.1. Isolation Forest<br>
>2.2. Local Outlier Factor
3. Supervised Learning - Classification
>3.1. Logistic Regression<br>
>3.2. Random Forest<br>
>3.3. Support Vector Machines
4. Autoencoder - Unsupervised and  Semi-Supervised Learning
>4.1. Unsupervised Learning<br>
>4.2. Semi-Supervised Learning<br>

<br>
<br>

# Data Set

This dataset is from Kaggle website and can be found though the link:

https://www.kaggle.com/mlg-ulb/creditcardfraud


Below the data description from the original source.

<br>
<br>

## Context
It is important that credit card companies are able to recognize fraudulent credit card transactions so that customers are not charged for items that they did not purchase.

<br>

## Content
The datasets contains transactions made by credit cards in September 2013 by european cardholders.
This dataset presents transactions that occurred in two days, where we have 492 frauds out of 284,807 transactions. The dataset is highly unbalanced, the positive class (frauds) account for 0.172% of all transactions.

It contains only numerical input variables which are the result of a PCA transformation. Unfortunately, due to confidentiality issues, we cannot provide the original features and more background information about the data. Features V1, V2, … V28 are the principal components obtained with PCA, the only features which have not been transformed with PCA are 'Time' and 'Amount'. Feature 'Time' contains the seconds elapsed between each transaction and the first transaction in the dataset. The feature 'Amount' is the transaction Amount, this feature can be used for example-dependant cost-senstive learning. Feature 'Class' is the response variable and it takes value 1 in case of fraud and 0 otherwise.

<br>

## Inspiration
Identify fraudulent credit card transactions.

Given the class imbalance ratio, we recommend measuring the accuracy using the Area Under the Precision-Recall Curve (AUPRC). Confusion matrix accuracy is not meaningful for unbalanced classification.

<br>

## Acknowledgements
The dataset has been collected and analysed during a research collaboration of Worldline and the Machine Learning Group (http://mlg.ulb.ac.be) of ULB (Université Libre de Bruxelles) on big data mining and fraud detection.
More details on current and past projects on related topics are available on https://www.researchgate.net/project/Fraud-detection-5 and the page of the DefeatFraud project

<br>

**Please cite the following works:**

Andrea Dal Pozzolo, Olivier Caelen, Reid A. Johnson and Gianluca Bontempi. Calibrating Probability with Undersampling for Unbalanced Classification. In Symposium on Computational Intelligence and Data Mining (CIDM), IEEE, 2015

Dal Pozzolo, Andrea; Caelen, Olivier; Le Borgne, Yann-Ael; Waterschoot, Serge; Bontempi, Gianluca. Learned lessons in credit card fraud detection from a practitioner perspective, Expert systems with applications,41,10,4915-4928,2014, Pergamon

Dal Pozzolo, Andrea; Boracchi, Giacomo; Caelen, Olivier; Alippi, Cesare; Bontempi, Gianluca. Credit card fraud detection: a realistic modeling and a novel learning strategy, IEEE transactions on neural networks and learning systems,29,8,3784-3797,2018,IEEE

Dal Pozzolo, Andrea Adaptive Machine learning for credit card fraud detection ULB MLG PhD thesis (supervised by G. Bontempi)

Carcillo, Fabrizio; Dal Pozzolo, Andrea; Le Borgne, Yann-Aël; Caelen, Olivier; Mazzer, Yannis; Bontempi, Gianluca. Scarff: a scalable framework for streaming credit card fraud detection with Spark, Information fusion,41, 182-194,2018,Elsevier

Carcillo, Fabrizio; Le Borgne, Yann-Aël; Caelen, Olivier; Bontempi, Gianluca. Streaming active learning strategies for real-life credit card fraud detection: assessment and visualization, International Journal of Data Science and Analytics, 5,4,285-300,2018,Springer International Publishing

Bertrand Lebichot, Yann-Aël Le Borgne, Liyun He, Frederic Oblé, Gianluca Bontempi Deep-Learning Domain Adaptation Techniques for Credit Cards Fraud Detection, INNSBDDL 2019: Recent Advances in Big Data and Deep Learning, pp 78-88, 2019

Fabrizio Carcillo, Yann-Aël Le Borgne, Olivier Caelen, Frederic Oblé, Gianluca Bontempi Combining Unsupervised and Supervised Learning in Credit Card Fraud Detection Information Sciences, 2019
