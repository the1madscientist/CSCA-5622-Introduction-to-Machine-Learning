# MSCS_SL_FinalPorject
A final project for MSCS introduction to ML, Supervised Learning.
TABLE OF CONTENTS

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

## Forward
Welcome to the Starship Titanic ML Project! This repository contains my final project for CSCA 5622 Introduction to machine learning, supervised learning.
I have decided to join a Kaggle competition classifying data centered around the mysterious voyage of the Starship Titanic. The challenge here is to build
a classification model that predicts which passengers were transported through a wormhole to another galaxy and which ones perished during the accident. 
By leveraging machine learning techniques, I aim to analyze the provided dataset to uncover patterns and build an effective predictive model for this 
captivating scenario. Dive in to explore the code, methods, and insights gained throughout my journey!, I hope you enjoy!

## Introduction

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


## Dataset Overview

The dataset for this competition consits of 3 CSV files. The trainnig set consits of the following features: PassengerId,	HomePlanet,	CryoSleep,	Cabin,	
Destination,	Age,	VIP,	RoomService,	FoodCourt, ShoppingMall,	Spa, VRDeck,	Name,	and Transported (the desired output). There is also a sample submission
file showing the required output format. And finally the test dataset with teh same features as the training set, sans the transported column.   

Data Exploration

To understand the data set I first started by importing the CSV to a pandas dataset. Then just a simple .head() and .info() on the dataset to get a basic 
structure. After that some visualizations including a heatmap of the correlation matrix, and finally a full set of distribution plots for all of the numeric 
data. Finally I put eyes directly on the dataset. This was much more helpful than I expected, as there were several instances of missing data, and logical 
ways to replace the data in a much more accurate way than just most common. 

Data Preprocessing

To start with using the insight gained from putting eyes directly on the csv files. When I realized that about half of the missing values in the cryro sleep
feature (T or F), could be easily filled in for those who spent money. If they spent money, then they couldnt be in stasis. Also a few other things stuck out,
like cabin numbers included which side the cabin was on (port or starboard). Also the passenger ID was comprised of two parts, the family number shared by 
multiple people in the same room, and guest number, so correcting data that was shared within each cabin, like destination and origin. So I created a data 
cleaning function that automates the process of cleaning whatever dataset that is passed to it. 

Feature Engineering

Describe the feature engineering process, including any new features created, feature selection, and rationale behind these decisions.

Model Selection

Discuss the different models considered for the classification task, including why certain models were chosen or discarded. Mention any hyperparameter tuning performed.

Training and Evaluation

Provide details on how the models were trained, evaluation metrics used, and validation techniques applied (e.g., cross-validation).

Results

Summarize the performance of the final model(s) and discuss the results, including metrics like accuracy, precision, recall, and F1-score.

Conclusion

Conclude with key takeaways from the project, including insights gained and the overall effectiveness of the model.

Future Work

Suggest possible future improvements or additional analyses that could be done to enhance the model or explore the dataset further.
