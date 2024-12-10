# CSCA 5622 Introduction to Machine Learning Final Project
## A final project for MSCS introduction to ML, Supervised Learning.
## TABLE OF CONTENTS

Forward

Introduction

Dataset Overview

Data Exploration

Data Preprocessing

Feature Engineering

Model Selection

Training and Evaluation

Results

Conclusion

Future Work

References

### Forward
Welcome to the Starship Titanic ML Project! This repository contains my final project for CSCA 5622 Introduction to machine learning, supervised learning.
I have decided to join a Kaggle competition classifying data centered around the mysterious voyage of the Starship Titanic. The challenge here is to build
a classification model that predicts which passengers were transported through a wormhole to another galaxy and which ones perished during the accident. 
By leveraging machine learning techniques, I aim to analyze the provided dataset to uncover patterns and build an effective predictive model for this 
captivating scenario. Dive in to explore the code, methods, and insights gained throughout my journey!, I hope you enjoy!

### Introduction

Durring my time here working on this classification problem, I hope to utilize the knowledge gained from my coursework on supervised learning to create
a model, or multiple models to classify the data in the problem set. I will then submit myself to to competition to measure my progress against the field 
of competitiors. 

For context, and a problem outline, here is an excert from the kaggle competition description page:

Welcome to the year 2912, where your data science skills are needed to solve a cosmic mystery. We've received a transmission from four lightyears away and 
things aren't looking good.

The Spaceship Titanic was an interstellar passenger liner launched a month ago. With almost 13,000 passengers on board, the vessel set out on its maiden 
voyage transporting emigrants from our solar system to three newly habitable exoplanets orbiting nearby stars.

While rounding Alpha Centauri en route to its first destination—the torrid 55 Cancri E—the unwary Spaceship Titanic collided with a spacetime anomaly hidden
within a dust cloud. Sadly, it met a similar fate as its namesake from 1000 years before. Though the ship stayed intact, almost half of the passengers were 
transported to an alternate dimension!

To help rescue crews and retrieve the lost passengers, you are challenged to predict which passengers were transported by the anomaly using records recovered
from the spaceship’s damaged computer system.

Help save them and change history!


### Dataset Overview

The dataset for this competition consits of 3 CSV files. The trainnig set consits of the following features: PassengerId,	HomePlanet,	CryoSleep,	Cabin,	
Destination,	Age,	VIP,	RoomService,	FoodCourt, ShoppingMall,	Spa, VRDeck,	Name,	and Transported (the desired output). There is also a sample submission
file showing the required output format. And finally the test dataset with teh same features as the training set, sans the transported column.   

### Data Exploration

To understand the data set I first started by importing the CSV to a pandas dataset. Then just a simple .head() and .info() on the dataset to get a basic 
structure. After that some visualizations including a heatmap of the correlation matrix, and finally a full set of distribution plots for all of the numeric 
data. Finally I put eyes directly on the dataset. This was much more helpful than I expected, as there were several instances of missing data, and logical 
ways to replace the data in a much more accurate way than just most common. 

### Data Preprocessing

To start with using the insight gained from putting eyes directly on the csv files. When I realized that about half of the missing values in the cryro sleep
feature (T or F), could be easily filled in for those who spent money. If they spent money, then they couldnt be in stasis. Also a few other things stuck out,
like cabin numbers included which side the cabin was on (port or starboard). Also the passenger ID was comprised of two parts, the family number shared by 
multiple people in the same room, and guest number, so correcting data that was shared within each cabin, like destination and origin. So I created a data 
cleaning function that automates the process of cleaning whatever dataset that is passed to it. I also ran through normalization, centering and scaling 
functions, but found they did not improve my accuracy in any meaningful way (nore did they decrease the accuracy much). I will need to delve deeper into the 
topic to feel comfortable enough to determine how to best utilize normalizing and scaling preprocessors.

### Feature Engineering

For feature engineering, in the end it mostly became a manual process. Every automated feature extraction, simplification, normalization ended up not improving my 
models accuracy. So in the end I was just stuck with the data cleaning method I created, which also splits up the categorical daata into its respective truth tables

### Model Selection Training and Evaluation

I decided to run the gamut as far as models go and created a function that runs through 4 different supervised learning models. the models choosen were: logistic 
regression, K-nearest neighbor, random forest, and the support vector classifier. The function itterates through each one, and using a parameter dictionary and 
GridCV, iterates through the models with 5 fold cross validation to test each classifier through multiple hyperparameter settings and returns a confusion matrix 
and other relevant scores. This proved to be most useful and time saving in the end when I was trying so very hard to wring every last bit of performance out of 
my submissions. 

### Results

In the end my model did compare closely with the majority of the participants at 79.5% accuracy, but did not land anywhere near the top 3 the leaderboard (83% - 95%). 
I was satisfied with the performace of my model, esspecially as it was my first entry into a Kaggle competion. Also I felt like there are better models to use in 
the deep learning category, but as this is a supervised learning course, I felt it appropriate to limit myself to models learned durring the course.

### Conclusion

I found this project, frustrating at times, and time consuming, and also very rewarding. The knowlege gained is better than I expected. I was happy with the results
even though I did not end up being a top contender. I was able to compete, and create a working model. I will definately be using kaggle again in the future in my
spare time to improve my machine learning skills. I had a lot of fun with this one, and am glad I chose this direction. 

Some key takeaways I would like to share would be:
1. Eyes on the raw data, especially with categorical and numerical mixed data can shed light on methods for data cleaning and processing.
2. Automate early and often, this has always been one of my pitfalls. Trying to do everything manualy for as long as possible instead of taking the time to
automate from the word go.
3. leverage existing libraries to simplify, and speed up the process. I did find it useful throughout the course building some of these models essentially from
scratch to understnd them better. But utilizing an existing library is so much faster.  

### Future Work

I will definately continue this project in the future, as I learn more techniques for data processing, and use of more advance deep learning methods. It has kept 
my attention this entire time, and I beleive I can do better. 

## References

OpenAI. (2024, November 20 - December 09). ChatGPT [Large language model]. Retrieved from https://chat.openai.com/

GeeksforGeeks. (n.d.). Data Preprocessing in Machine Learning using Python. Retrieved December 01, 2024, from https://www.geeksforgeeks.org/data-preprocessing-machine-learning-python/

Built In. (n.d.). Supervised Learning in Python. Retrieved December 01, 2024, from https://builtin.com/data-science/supervised-learning-python

GeeksforGeeks. (n.d.). How to Normalize Data Using Scikit-Learn in Python. Retrieved December 03, 2024, from https://www.geeksforgeeks.org/how-to-normalize-data-using-scikit-learn-in-python/

