Crop Recommendation System (NPK and Weather Based)

Project Overview
This project is a Machine Learning based Crop Recommendation System that predicts the most suitable crop to grow based on soil nutrient values and weather parameters. The system uses an Ensemble Model combining RandomForest and CatBoost classifiers to achieve higher prediction accuracy. The trained model is integrated into a full-stack web application using Flask as the backend API and React JS as the frontend user interface.

Dataset
Dataset Source: Kaggle
Dataset Name: Crop Recommendation Dataset
Kaggle Dataset: atharvaingle/crop-recommendation-dataset

Input Features
N: Nitrogen
P: Phosphorus
K: Potassium
temperature
humidity
ph
rainfall

Output Label
label: Crop name recommended by the model

Project Objectives
The main objectives of this project are to recommend the best crop based on soil nutrient and climate inputs, implement RandomForest and CatBoost machine learning models, develop an Ensemble Model using soft voting technique, deploy the model using a Flask REST API, and build a responsive React website for user interaction.

Technologies Used
Machine Learning
Python
pandas
numpy
scikit-learn
catboost
joblib

Backend
Flask
Flask-CORS

Frontend
React JS
Fetch API

System Architecture
The user enters input values such as N, P, K, temperature, humidity, pH, and rainfall on the React website. The frontend sends a request to the Flask API endpoint. The backend loads the saved Ensemble model and Label Encoder, performs prediction, and returns the recommended crop name along with confidence value. The frontend displays the output in the result section.

Folder Structure
crop-project
backend
app.py
ensemble_crop_model.pkl
label_encoder.pkl
requirements.txt
frontend
React application files

Installation and Setup

Step 1: Clone the Repository
git clone <your-repo-link>
cd crop-project

Step 2: Backend Setup (Flask API)
cd backend
pip install -r requirements.txt
python app.py

Backend will run at http://127.0.0.1:5000

Step 3: Frontend Setup (React UI)
cd frontend
npm install
npm start

Frontend will run at http://localhost:3000

API Details

Endpoint
POST /predict

Request JSON Format
{
"N": 90,
"P": 42,
"K": 43,
"temperature": 25,
"humidity": 80,
"ph": 6.5,
"rainfall": 200
}

Response JSON Format
{
"recommended_crop": "rice",
"confidence": 98.24
}

Model Training (Google Colab)
The model was trained on the Kaggle Crop Recommendation Dataset. Data preprocessing includes checking missing values, separating features and label, label encoding the crop names, and splitting into training and testing datasets. Two models were trained: RandomForestClassifier and CatBoostClassifier. An Ensemble VotingClassifier using soft voting technique was built by combining both models. The trained Ensemble model and Label Encoder were saved using joblib.

Saved Files
ensemble_crop_model.pkl
label_encoder.pkl

These files are used in the Flask backend for prediction.

Results
The trained RandomForest model and CatBoost model provided high accuracy. The Ensemble model achieved the best performance and improved prediction stability. The system outputs the crop name and confidence score for the given soil and climate values.

Future Enhancements
This project can be enhanced by adding fertilizer recommendation based on nutrient deficiency, integrating real-time weather API for automatic climate values, storing user inputs and predictions in a database, providing top 3 crop predictions with probabilities, and developing a mobile application version.

Author
Developed by: <Your Name>
Project Type: Crop Recommendation System using Machine Learning and Web Integration
