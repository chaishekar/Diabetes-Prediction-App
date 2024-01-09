# Diabetes Checkpoint Pro App
This project diagnostically predicts whether or not a patient has diabetes based on healthcare statistics and lifestyle survey information.

In terms of problem type, this project focuses on classification. Specifically, it involves categorizing individuals into two distinct groups: those who have diabetes and those who do not. This binary classification task leverages healthcare statistics and lifestyle survey data to predict a patient's diabetes status.

## Data Description
The Diabetes Health Indicators Dataset is a dataset obtained from the UCI Repository (link to access the dataset: https://github.com/uci-ml-repo/ucimlrepo). This dataset includes a wide variety of healthcare information and lifestyle survey responses from individuals, as well as their diabetes diagnosis. Specifically, it comprises 21 features, including demographic information, laboratory test results, and survey answers for each patient. The main target variable for classification purposes is the distinction between patients with diabetes (including pre-diabetic individuals) and those who are healthy. Initially, the feature and target variables were extracted and subsequently merged into a single dataset, resulting in a total dataset size of 253,680 records.

## Data Preprocessing

In this stage of the project, duplicates were removed, missing values were checked, resampling was done, and feature engineering was performed wherein 'BMI_category' feature and 'lifestyle_score' were engineered. Check out the [MLmodel.ipynb](MLmodel.ipynb) file for the code.

## Exploratory Data Analysis 

The correlation of the features in the dataset with the target variable was analyzed using heatmaps, bar plots, violin plots, and density plots. The code for EDA is in the [MLmodel.ipynb](MLmodel.ipynb) file.

## Model Building

In this project, we conducted a classification routine utilizing a variety of machine-learning algorithms to predict diabetes status:

1. Logistic Regression
2. Decision Tree Classifier
3. Gaussian Naive Bayes (GaussianNB)
4. Random Forest Classifier
5. Bagging Classifier
6. Gradient Boosting Classifier
7. XGBoost Classifier

For the evaluation of these models, we employed various performance metrics, including accuracy, precision, recall, and the F1-score. To facilitate a comparative analysis of each model's performance, we have created box plots, confusion matrices, and bar plots. To fine-tune the model's behavior, grid search CV was employed for hyperparameter tuning.

Additionally, we've built a stacked classifier to leverage the combined strength of multiple models. The best classifier serves as the level 1 classifier, and logistic regression is used as the level 0 classifier in this ensemble model.

#### Best Classifier

The best classifier model XGBoost classifier, is saved as "best_classifier.pkl." This model can be used for making predictions on new data.

For detailed code and implementation, please refer to the [MLmodel.ipynb](MLmodel.ipynb) file.

## Flask Initialization

To set up and run the Flask application locally, follow these steps:

#### Create a Virtual Environment

Create a virtual environment to isolate your project's dependencies. Use the following command:
`python -m venv venv`

#### Activate the Virtual Environment (Mac/Linux)

Activate the virtual environment using the source command. This ensures you're working within the isolated environment.
`source venv/bin/activate`

#### Install Dependencies

All required libraries are listed in the requirements.txt file. Install them with pip using the following command:
`pip install -r requirements.txt`

#### Run the Flask Application

To start the Flask application, run the following command:
`flask run`

## Directory Structure

```bash
.
├── README.md
├── .gitignore
├── MLmodels.ipynb
├── Procfile
├── requirements.txt
├── runtime.txt
├── wsgi.py
├── venv/ #saved locally
└── app/
     ├── app.py
     ├── static/  # Images are saved here
     ├── model/ 
     │    └── best_classifier.pkl
     └── templates/
          ├──index.html
          └──form.html
```

## Deployment

The app is deployed on Heroku at [link](https://diabetesprediction-bb75d93351b1.herokuapp.com/)

#### App Demo:
![app demo](appdemo.gif)





