### Table of Contents

1. [Installation](#installation)
2. [Project Motivation](#motivation)
3. [File Description](#files)
4. [Execution](#execution)
5. [Licensing](#license)

## Installation <a name="installation"></a>
In addition to the standard libraries, following installations will be needed: 
plotly
nltk
flask
fklearn
fqlalchemy
fys
re
pickle

## Project Motivation  <a name="motivation"></a>
The purpose of the project is to build a model for an API that classifies disaster messages. Using the web app an emergency worker can input a new message and get classification results in several categories so to have an idea what kind of help is needed: "water", "shelter", "food", etc.

## File Descriptions  <a name="files"></a>
process_data.py: The code performs extraction of the messages and categories dataset and merges them into one dataset. Cleaning of the raw dataset is performed by applying 
transformation and finally it is loaded into SQLite database
    
train_classifier.py: In this file, data is loaded from SQLite database, model is build by creating a pipeline and then training and tuning the model using grid search. Finally the model is evaluated on the f1 score

run.py : The code in this file is used to create a flask webapp

## Execution:  <a name="execution"></a>
1. Run the following commands in the project's root directory to set up your database and model.
    >> To run ETL pipeline that cleans data and stores in database python data/process_data.py data/disaster_messages.csv data/disaster_categories.csv data/DisasterResponse.db
    
    >> To run ML pipeline that trains classifier and saves python models/train_classifier.py data/DisasterResponse.db models/classifier.pkl
2. Run the following command in the app's directory to run your web app. python run.py

3. Go to http://0.0.0.0:3001/

## Licensing  <a name="license"></a>
This app was completed as part of the Udacity Data Scientist Nanodegree. Code templates and data were provided by Udacity. The data was originally sourced by Udacity from Figure Eight.
