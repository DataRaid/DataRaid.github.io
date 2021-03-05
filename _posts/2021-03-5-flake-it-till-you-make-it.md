---
layout: post
title: World Nation's Income
subtitle: Incomes calculated by The WorldBank
cover-img: /assets/img/world.jfif
thumbnail-img: /assets/img/world.jfif
share-img: /assets/img/path.jpg
tags: [Python]
---

Background:This data classifies all World Bank member countries (189), and all other economies with populations of                         more than 30,000.
-For operational and analytical purposes, economies are divided among income groups according to 2019 gross national income (GNI) per capita, calculated using the World Bank Atlas method. 
-The groups are: low income, $1,035 or less; lower middle income, $1,036 - 4,045; upper middle income, $4,046 - 12,535; and high income, $12,536 or more. 

Data Description: This 2019 data is obtained from the WorldBank.It allows classification of countries into income groups - low, lower-middle, upper-middle and high - by gross national income (GNI) per capita, in U.S. dollars.The limitations are that it does not represent  each nation's stability to maintain growth and overall population happiness.

My hypothesis was that 60% of the world's nations are living under low income.
There were a few NANS which were removed.Dropped rows which the data was just a single variable. Calculated the array percentage. 
This was a very simple data with little to feature engineer but served as pratice to help remember analysis codes.

The data results were very different from what I hypothesized. About 14% is actually livng under low GNI. The middle income group takes about 50% of the worlds nation and about 37% is of high income.

![Graph](/assets/img/graph.png)












![Map](/assets/img/pic.PNG)


![Legend](/assets/img/pic2.PNG)


It would be a good inclusion to add data of the cost of living in each country to see a glimpse of how it compares from their GNI.

sources:https://datahelpdesk.worldbank.org/knowledgebase/articles/906519, https://www.kaggle.com/taniaj/world-bank-country-and-lending-groups, https://datatopics.worldbank.org/world-development-indicators/the-world-by-income-and-region.html
