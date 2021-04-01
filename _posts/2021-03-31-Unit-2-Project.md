---
layout: post
title: Machine Learning With Olist Data
subtitle: How will you pay?
cover-img: /assets/img/Brazil.PNG
thumbnail-img: /assets/img/Brazil.PNG
share-img: /assets/img/Brazil.png
tags: [Python]
---
<h3>The largest ecommerce marketplace of Brazil</h3>

Olist is the largest department store in the Brazilian marketplaces. 
Olist connects small businesses from all over Brazil to channels without hassle and with a single contract. 
Those merchants are able to sell their products through the Olist Store and ship them directly to the customers using Olist logistics partners.
After a customer purchases the product from Olist Store a seller gets notified to fulfill that order. Once the customer receives the product, 
or the estimated delivery date is due,the customer gets a satisfaction survey by email where he can give a note for the purchase experience and write down some comments.


<h3>Data Collection:</h3>
The data was obtained from the public dataset of orders made at Olist Store. 
This data contains information of over 100k orders made between 2016 and 2018 by multiple marketplaces in Brazil.
It contains 8 data frames each allowing the viewing of multiple dimensions ranging from order status, price, payment and freight performance to customer location,
product attributes, geolocation dataset that relates Brazilian zip codes to lat/lng coordinates and finally reviews written by customers.


<h3>Pre-feature engineering data:</h3>
The data with all 8 data frames combined was massive. It has about 52 features and over 100k observations.
It was key to create an app.creatly.com diagram and carefully select which data frames contained key information in regards to my target feature and 
which features each data frame shared for a merge.



![Diagram](/assets/img/chartapply.PNG)




<h3>Cleaning the data and feature engineering:</h3>

<li>I ended up using 4 columns out of the 8.</li>
<li>Each data frame was checked for null values and high cardinality categorical values </li>
<li>The high cardinality catergorical values were dropped in cases such as zipcodes and cities. Others
  which were needed in the model were lowered in cardinality.This was done to multiple features on varius data frames.</li>
<li>Each data frame used was indexed by either the product i.d or order i.d to make the merging easier.</li>
<li>The merging was done on the indexes and with an inner merge.</li>
<li>The final data frame consisted of 100k observations and 7 features.
<li>The target feature in the last data frame created by the merge was modified to be a binary column having credit card 
  payment as main feature instead of having three others.
  
<h3>Splitting and Classification Modeling with Hypertuning</h3>

<li>The target of my prediction was credit card payment method.</li>
<li> I dropped the target column for the validation data and did a train_test_split(X, y, test_size=0.2, random_state=42).</li>
<li> My baseline prediction was 74%.
<li> For my binary classification I started using RandomForestClassifier with n_estimators=60, n_jobs=-1, random_state=42.
  This yielded a 99% train accuracy score and a 81% validation acc. A clear overfitting problem.</li>
<li> I ended up using XGBoost with the parameters:n_estimators=100, max_depth=10, learning_rate=1e-3 and n_jobs=10.
  Tuning these parameters made a huge difference in my scores.</li>
<h3>Results:</h3>

The scores obtained in the XGBoost model where significantly better than the randomforestclassifier giving an 81% training accuracy and a 80% 
validation accuracy. Below is the 10 most important features in my model based on the reduction in gini impurity.



![v](/assets/img/gini.PNG) 








![x](/assets/img/confusion.PNG)





![y](/assets/img/score.PNG)





<li>The model correctly predicted 18494 predictions and 4594 incorrectly. About an 80% accuracy compared to the base of 74%.</li>
<h3> Conclusion</h3>
This model may have more room for improvement with tweaking the parameters even more and perhaps even using some data left out in other 
data frames not used. Overall, i believe it is a good model for predicting if the customer will pay using a credit card at the checkout when shopping
at Olist. This prediction can be used for implementing credit card offers to the customer that may be better than the ones they were planning to use
for the payment while at checkout. This could be a business plan with banks that may be beneficial for all parties.
 
