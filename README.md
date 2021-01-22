# Disaster Response Pipeline Project <br>

Table of Contents<br>

 1.Installation<br>
 2.Project Motivation<br>
 3.Project Descriptions<br>
 4.Files Descriptions<br>
 5.Instructions<br>

Installation:<br>

All libraries are available in Anaconda distribution of Python. The used libraries are:<br><br>

pandas<br>
re<br>
sys<br>
json<br>
sklearn<br>
nltk<br>
sqlalchemy<br>
pickle<br>
Flask<br>
plotly<br>
sqlite3<br>
The code should run using Python versions 3.*.<br>

Project Motivation<br>

The goal of the project is to classify the disaster messages into categories. In this project, I analyzed disaster data from Figure Eight to build a model for an API that classifies disaster messages. Through a web app, the user can input a new message and get classification results in several categories. The web app also display visualizations of the data.<br>

Project Descriptions<br>

The project has three components which are:<br>

1.ETL Pipeline: process_data.py file contain the script to create ETL pipline which:<br>
    a.Loads the messages and categories datasets<br>
    b.Merges the two datasets<br>
    c.Cleans the data<br>
    d.Stores it in a SQLite database<br>
    
    
2.ML Pipeline: train_classifier.py file contain the script to create ML pipline which:<br>
    a.Loads data from the SQLite database<br>
    b.Splits the dataset into training and test sets<br>
    c.Builds a text processing and machine learning pipeline<br>
    d.Trains and tunes a model using GridSearchCV<br>
    e.Outputs results on the test set<br>
    f.Exports the final model as a pickle file<br>
    
    
3.Flask Web App: The web app enables the user to enter a disaster message, and then view the categories of the message.<br>

The web app also contains some visualizations that describe the data.<br>

Files Descriptions:<br>

The files structure is arranged as below:<br>

- app<br>
| - template<br>
| |- master.html  # main page of web app<br>
| |- go.html  # classification result page of web app<br>
|- run.py  # Flask file that runs app<br>

- data<br>
|- disaster_categories.csv  # data to process <br>
|- disaster_messages.csv  # data to process<br>
|- process_data.py<br>
|- DisasterDatabase.db   # database to save clean data to<br>

- models<br>
|- train_classifier.py<br>
|- classifier.pkl  # saved model<br> 

- README.md<br>

### Instructions:<br>
1. Run the following commands in the project's root directory to set up your database and model.<br>

    - To run ETL pipeline that cleans data and stores in database<br>
        `python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterDatabase.db`<br>
    - To run ML pipeline that trains classifier and saves<br>
        `python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl`<br>

2. Run the following command in the app's directory to run your web app.<br>
    `python run.py`<br>

3. Go to http://0.0.0.0:3001/<br>
