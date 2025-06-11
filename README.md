# Forecasting Daily Temperatures in Paris with Deep Learning, EDA, API & Dockerized EC2 Deployment

Development of a complete pipeline to forecast daily temperatures in Paris using meteorological data.  
The project includes Exploratory Data Analysis (EDA), Deep Learning modeling, deployment via an API, and a user interface built with Gradio — all hosted on an EC2 server with Docker.

## Introduction

This project aims to forecast daily temperatures in Paris using hourly weather data (humidity, wind, cloud cover, etc.).  
We start by exploring patterns and correlations between variables using advanced EDA techniques.  
The objective is to design a predictive deep learning model and deploy it in production using:
- SHAP for the model explainability
- a Gradio interface for end-users
- a FastAPI backend
- Docker and AWS EC2 for cloud deployment

## Project structure
```
📁 Temperatures_forecasting/
├── 📊 Temperatures_forecasting.ipynb .................... Full exploratory analysis (EDA)
├── 🤖 model_training.ipynb ........ Model design and training
├── 🧪 evaluation.ipynb ............ Model testing and validation
├── 🧰 requirements.txt ............ Required Python libraries
├── 🚀 app/ ........................ API and Gradio interface
└── 🐳 docker/ ...................... Docker setup and deployment
└── .gitignore ...................... Files to ignore
```
## Data

The dataset is sourced from Météo-France via the Open-Meteo.com API. It contains hourly weather observations in Paris over a 10-year period, ranging from January 1st, 2015 at 00:00 to January 1st, 2025 at 23:00. The timezone is Europe/Berlin or Europe/Paris. The latitude is 2.35° and the longitude is 48.85°. You can retrieve the data from the following link : https://open-meteo.com/en/docs/meteofrance-api#location_and_time.
Each record includes the following variables:

- Date and time (hourly resolution — 24 values per day),
- Temperature (2m in °C),
- Humidity (2m in %),
- Cloud cover (in %),
- Wind speed (10m in km/h),
- Wind direction (10m in degrees, indicating the direction the wind is coming from).

This temporal dataset is ideal for time series analysis and modeling tasks such as temperature forecasting.

## Exploratory Data Analysis (EDA)

The exploratory analysis is detailed in the notebook `Temperatures_forecasting.ipynb`.  
It focuses on identifying temporal patterns and relationships between weather variables such as humidity, wind, and cloud cover, and how they relate to temperature.

Key steps include:
- Temporal analysis of each variable (daily and seasonal trends)
- Correlation analysis to detect linear relationships, especially with temperature
- Wind rose and directional wind speed analysis
- Feature engineering using cyclic encodings (sin/cos) of time variables
- Visualizations to support variable selection for forecasting

This step helps determine which variables and transformations are most relevant for the prediction model.

## Deep Learning modelization

## Model Explainability with SHAP
