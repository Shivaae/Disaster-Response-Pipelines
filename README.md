# Disaster Response Pipeline Project

Table of Contents
 1.Installation
 2.Project Motivation
 3.Project Descriptions
 4.Files Descriptions
 5.Instructions

Installation

All libraries are available in Anaconda distribution of Python. The used libraries are:

pandas
re
sys
json
sklearn
nltk
sqlalchemy
pickle
Flask
plotly
sqlite3
The code should run using Python versions 3.*.

Project Motivation

The goal of the project is to classify the disaster messages into categories. In this project, I analyzed disaster data from Figure Eight to build a model for an API that classifies disaster messages. Through a web app, the user can input a new message and get classification results in several categories. The web app also display visualizations of the data.

Project Descriptions

The project has three components which are:

1.ETL Pipeline: process_data.py file contain the script to create ETL pipline which:
    a.Loads the messages and categories datasets
    b.Merges the two datasets
    c.Cleans the data
    d.Stores it in a SQLite database
2.ML Pipeline: train_classifier.py file contain the script to create ML pipline which:
    a.Loads data from the SQLite database
    b.Splits the dataset into training and test sets
    c.Builds a text processing and machine learning pipeline
    d.Trains and tunes a model using GridSearchCV
    e.Outputs results on the test set
    f.Exports the final model as a pickle file
    
3.Flask Web App: The web app enables the user to enter a disaster message, and then view the categories of the message.

The web app also contains some visualizations that describe the data.

Files Descriptions:

The files structure is arranged as below:

- app
| - template
| |- master.html  # main page of web app
| |- go.html  # classification result page of web app
|- run.py  # Flask file that runs app

- data
|- disaster_categories.csv  # data to process 
|- disaster_messages.csv  # data to process
|- process_data.py
|- DisasterDatabase.db   # database to save clean data to

- models
|- train_classifier.py
|- classifier.pkl  # saved model 

- README.md

### Instructions:
1. Run the following commands in the project's root directory to set up your database and model.

    - To run ETL pipeline that cleans data and stores in database
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db`
    - To run ML pipeline that trains classifier and saves
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`

2. Run the following command in the app's directory to run your web app.
    `python run.py`

3. Go to http://0.0.0.0:3001/
