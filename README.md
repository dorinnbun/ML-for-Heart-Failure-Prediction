# ML-for-Heart-Failure-Prediction



# Project Overview

This project addresses the challenge of early heart disease detection.

**Problem Statement**: To build a supervised machine learning model that accurately predicts the presence of heart disease in a patient based on a set of clinical features. This is a binary classification task.

**Relevance:** Heart disease is a leading global cause of death. An accurate predictive tool can empower healthcare professionals to identify at-risk individuals sooner, enabling timely intervention and potentially saving lives.

The project follows these key steps:

1. **ETL (Extract, Transform, Load**): Data is loaded, cleaned, and preprocessed.
2. **Modeling**: A Random Forest Classifier is trained on the prepared data.
3. **Hyperparameter Tuning**: GridSearchCV is used to perform an exhaustive search over a parameter grid with 5-fold cross-validation.
4. **Evaluation**: The model's performance is assessed using metrics suitable for imbalanced data, such as Precision, Recall, and the Precision-Recall Area Under Curve (PR-AUC).

## Dataset

This project uses the "Heart Failure Prediction" dataset from Kaggle.

**Source:** https://www.kaggle.com/datasets/fedesoriano/heart-failure-prediction?resource=download

**Content:** It contains **918 records** and **12 columns**, including a mix of numerical and categorical features like **Age, Sex, ChestPainType, RestingBP, Cholesterol, and MaxHR**. The target variable is HeartDisease, where 1 indicates the presence of disease and 0 indicates its absence.

## How to Run This Project on a Virtual Server
This guide explains how to set up and run the project on a remote Linux server.

### 1. Initial Server Setup
First, connect to your server via SSH. Then, install the necessary tools.

### Update package lists
sudo apt update && sudo apt upgrade -y

### Install Python, pip, venv, and Git
sudo apt install python3-pip python3-venv git jupyterlab -y

### 2. Clone the Project Repository
Clone this repository to your server. Navigate into the ML directory!

git clone https://github.com/
cd ML

### 3. Set Up the Python Environment
Create a virtual environment to manage the project's dependencies.

### Create a virtual environment
python3 -m venv venv

### Activate the environment
source venv/bin/activate

### Install the required libraries
pip install -r requirements.txt

### 4. Run Jupyter Lab in a Session
To ensure your notebook keeps running even if you disconnect, use tmux.

### Install tmux
sudo apt install tmux -y

### Start a new tmux session
tmux new -s jupyter

## Inside the tmux session, start Jupyter Lab
## (Ensure your venv is still active)

jupyter lab --ip=0.0.0.0 --port=8888 --no-browser

## 5. Access and Run the Notebook
In your local web browser, navigate to http://yourip:8888.
When prompted, enter the token provided in your terminal output.
You can also enter the token directly on the url, for example: http://yourip:8888/lab?token=37a87ed0da1858c0942181220bc9c2c68bf634ce70ac17fc

Open the Final_Project.ipynb file and run the cells.
Note on Runtime: The hyperparameter tuning cell (Step 4 in the notebook) is computationally intensive. The time may varies depending on the specifications.

To safely detach from the tmux session, press Ctrl+b, then d.

## Key Results
The final model achieved strong performance on the unseen test set:
