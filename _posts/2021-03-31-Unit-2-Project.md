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
<li>I ended up using 4 columns out of the 8.
Each data frame was checked for null values, high cardinality categorical values.

