# SCORELAB

ScoreLab AI — Student Performance Predictor

An interactive machine-learning-inspired web experience for exploring how student academic factors can influence predicted final exam scores.

ScoreLab AI is designed as an educational frontend prototype. Users can change student characteristics, watch the predicted score update live, explore feature impact, compare "what-if" scenarios, and simulate a basic ML training pipeline.

✨ Features

Live student score prediction

Interactive sliders for:

Weekly study time

Previous grade G1

Previous grade G2

Absences

Past failures

Extra-support selector

Mathematics / Portuguese subject selector

Animated predicted-score orb

Dynamic confidence indicator

Low / medium / high risk classification

Feature-impact visualization

Student profile radar chart

Interactive score curves

Score vs study time

Score vs previous grade G2

"What-if" improvement engine

Ready-made student profiles:

Consistent

Last-minute

Top performer

Needs help

Animated ML pipeline:

Clean

Train

Evaluate

Built-in Python / scikit-learn starter code

Responsive design for desktop, tablet and mobile

Dark, modern glass-style interface

UCI dataset reference

🧠 Machine Learning Concept

The project is based on the UCI Student Performance dataset.

The real ML workflow demonstrated in the included Python example is:

Load the dataset with Pandas.

Select relevant student-performance features.

Split the data into training and testing sets.

Train a Linear Regression model using scikit-learn.

Generate predictions.

Evaluate the model using:

Mean Absolute Error (MAE)

Root Mean Squared Error (RMSE)

R² score

The target variable is G3, the student's final grade.

Example features used by the Python workflow:

studytime
failures
absences
G1
G2

⚠️ Important: Demo vs Real Model

The browser interface uses an illustrative scoring function so that predictions can update instantly without running Python in the browser.

Therefore, the number shown in the interactive UI should be treated as a demonstration of the ML concept, not as the output of a trained production model.

The included Python code shows how to train and evaluate an actual Linear Regression model using the dataset.

📊 Dataset

The project uses the UCI Student Performance dataset:

https://archive.ics.uci.edu/dataset/320/student%2Bperformance

The dataset contains student information and academic-performance variables for secondary-school students.

The project focuses particularly on the final grade G3 and variables such as study time, failures, absences, G1, and G2.

🛠️ Technologies

Frontend

HTML5

CSS3

JavaScript

Chart.js

Machine Learning

Python

Pandas

NumPy

Scikit-learn

Linear Regression

Matplotlib / visualization concepts

📁 Project Structure

scorelab-ai/
│
├── scorelab_ai_interactive.html
└── README.md

The main website is completely contained in:

scorelab_ai_interactive.html

No backend server is required to open the interactive prototype.

🚀 How to Run

Option 1 — Open directly

Simply double-click:

scorelab_ai_interactive.html

It will open in your browser.

Option 2 — Use VS Code

Open the project folder in VS Code.

Open scorelab_ai_interactive.html.

Install the Live Server extension if desired.

Right-click the HTML file.

Select Open with Live Server.

🐍 Running the Real ML Model

Install the required Python libraries:

pip install pandas numpy scikit-learn matplotlib

Download the UCI Student Performance dataset and place student-mat.csv in your working directory.

Then use the following workflow:

import pandas as pd
import numpy as np

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_absolute_error, mean_squared_error, r2_score

df = pd.read_csv("student-mat.csv", sep=";")

features = ["studytime", "failures", "absences", "G1", "G2"]

X = df[features]
y = df["G3"]

X_train, X_test, y_train, y_test = train_test_split(
    X,
    y,
    test_size=0.2,
    random_state=42
)

model = LinearRegression()
model.fit(X_train, y_train)

predictions = model.predict(X_test)

mae = mean_absolute_error(y_test, predictions)
rmse = np.sqrt(mean_squared_error(y_test, predictions))
r2 = r2_score(y_test, predictions)

print("MAE:", mae)
print("RMSE:", rmse)
print("R²:", r2)

📈 Evaluation Metrics

MAE — Mean Absolute Error

Measures the average absolute difference between the predicted and actual scores.

Lower is better.

RMSE — Root Mean Squared Error

Penalizes larger prediction errors more strongly than MAE.

Lower is better.

R² — Coefficient of Determination

Measures how much of the variation in the target can be explained by the model.

A value closer to 1 generally indicates a better fit.

🎨 Design Philosophy

ScoreLab AI intentionally avoids looking like a traditional static data dashboard.

The interface is designed as an interactive ML laboratory:

Explore → Change Inputs → Predict → Explain → Experiment → Evaluate

The goal is to make machine learning easier to understand visually, especially for students and beginners.

🔮 Possible Future Improvements

Connect the frontend to a real Python backend

Use an actual trained model for browser predictions

Add Random Forest and Gradient Boosting comparisons

Add real dataset visualizations

Display a confusion-style risk analysis

Add model feature coefficients

Add data-upload functionality

Add CSV export

Add model accuracy comparison

Add SHAP-based explainability

Add student-performance trend analysis

Deploy the project online

Add FastAPI/Flask backend

Store trained models with Joblib

📚 Learning Objectives

This project demonstrates the basic machine-learning lifecycle:

Dataset
   ↓
Data Cleaning
   ↓
Feature Selection
   ↓
Train/Test Split
   ↓
Model Training
   ↓
Prediction
   ↓
Evaluation
   ↓
Visualization

It is suitable as a beginner-friendly project for learning how Python, Pandas and Scikit-learn can be used to build a simple regression model.

👨‍💻 Project Status

Status: Interactive Educational Prototype

The frontend is functional and interactive. The next major upgrade would be connecting the interface to a real trained machine-learning model through a Python backend.

📄 License

This project is intended for educational and demonstration purposes.

Check the UCI Student Performance dataset page for the dataset's original terms and citation requirements.
