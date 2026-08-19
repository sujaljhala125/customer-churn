# Bank Customer Churn Prediction using Machine Learning, MLflow and Flask

An end-to-end Machine Learning project for predicting whether a bank customer is likely to churn based on customer demographics, account information, activity status, credit score, and other relevant features.

The project follows a modular Machine Learning pipeline covering data ingestion, data validation, data transformation, feature engineering, model training, and model evaluation. The trained model is integrated with a Flask web application to provide real-time customer churn predictions.

## Table of Contents

- [Project Overview](#project-overview)
- [Features](#features)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Running the Application](#running-the-application)
- [Usage](#usage)
- [Model Evaluation](#model-evaluation)
- [MLflow](#mlflow)
- [Future Improvements](#future-improvements)

---

## Project Overview

Customer churn is an important problem for banks because identifying customers who are likely to leave can help organizations take proactive retention measures.

This project predicts customer churn using features such as:

- Age
- Tenure
- IsActiveMember
- Gender
- Geography
- CreditScore
- NumOfProducts
- Balance
- EstimatedSalary
- HasCrCard

The dataset contains an imbalanced target variable, so **SMOTE (Synthetic Minority Over-sampling Technique)** is used to address class imbalance during model training.

Multiple Machine Learning models are evaluated, and the best-performing model is selected based on classification metrics such as:

- Accuracy
- Precision
- Recall
- F1-score

The project is organized as a modular pipeline to make the Machine Learning workflow easier to maintain, test, and extend.

---

## Features

### Data Ingestion
- Loads the customer churn dataset.
- Splits and prepares data for further processing.

### Data Validation
- Validates the dataset structure and required features.
- Checks data quality and consistency before model training.

### Data Transformation
- Performs preprocessing of numerical and categorical features.
- Applies required encoding and scaling techniques.
- Handles class imbalance using SMOTE.

### Feature Engineering
- Prepares relevant customer attributes for Machine Learning.
- Transforms raw customer information into model-ready features.

### Model Training
- Trains multiple Machine Learning algorithms.
- Compares model performance.
- Selects the best-performing model for prediction.

### Model Evaluation
The trained models are evaluated using:

- Accuracy
- Precision
- Recall
- F1-score

### MLflow
- Tracks Machine Learning experiments.
- Records model metrics and experiment information.
- Helps compare different model runs.

### Flask Web Application
- Provides a web interface for customer churn prediction.
- Accepts customer information as input.
- Returns the predicted churn result.

---

## Technologies Used

### Programming
- Python

### Machine Learning
- Scikit-learn
- SMOTE
- Pandas
- NumPy

### MLOps
- MLflow

### Web Development
- Flask
- HTML
- CSS

### Development Tools
- Git
- GitHub
- Conda
- VS Code

---

## Project Structure

```text
customer-churn/
│
├── artifacts/
│
├── data/
│
├── data_validation/
│
├── experiments/
│
├── src/
│
├── templates/
│
├── app.py
├── main.py
├── requirements.txt
├── setup.py
├── README.md
└── .gitignore

## Installation

1. Clone the repository:
    ```bash
    git clone https://github.com/sujaljhala125/customer-churn.git
    cd customer-churn
    ```

2. Create and activate the Conda environment:
    ```bash
    conda create --name churn_prediction python=3.10
    conda activate churn_prediction
    ```

3. Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```

## Running the Application

1. Run the Flask app:
    ```bash
    python app.py
    ```

2. The app will start on `http://127.0.0.1:5000/`.

### Flask URLs:
- **Default route** (`/`): For testing the app.
- **Prediction route** (`/predict`): Accepts input features for making predictions.

## Usage

Once the application is running, you can access the following:

- Default route: `http://127.0.0.1:5000/`
- Prediction route: `http://127.0.0.1:5000/predict`

You can use the `/predict` route to input features like `age`, `tenure`, `creditscore`, etc., and get back whether the customer is predicted to churn or not.

## Model Evaluation
The model was evaluated using various metrics:
- **Accuracy**  : 86%
- **Precision** : 66%
- **Recall**    : 62%
- **F1-score**  : 60%

The Gradient Boosting Classifier was found to be the best-performing model for predicting churn.
