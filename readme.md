# 🔋 Power Supply Forecasting Using LSTM

This project forecasts power supply for the next 5 days based on the last 5 days of usage data using an LSTM model. It was built as part of a Software Engineering class project using Kaggle and Flask.

---

## 🔍 Project Overview

The goal is to use historical power consumption data and weather readings (such as station pressure) to predict future consumption using an LSTM-based neural network. This can help in planning, energy optimization, and forecasting.

---

## 📊 Dataset

- **Source**: Excel file (`New Power.xlsx`) from the [Kaggle input directory](https://www.kaggle.com/)
- **Sheet Used**: `Sheet1`
- **Features Selected**:
  - `NET_P`: Net power consumption
  - `StnPres`: Station Pressure
- **Preprocessing**:
  - Converted `DATE` to datetime format
  - Sorted by date
  - Applied `MinMaxScaler`
  - Created `lag_1` and `lag_2` features for time-series prediction
  - Dropped `NaN` values

---

## 🤖 LSTM Model

- **Libraries**: 
  - `TensorFlow`, `Keras`, `scikit-learn`, `pandas`, `matplotlib`, `seaborn`
- **Model Structure**:
  - Input: Past 5 days of `NET_P` and `StnPres`
  - Layers: LSTM layer + Dense layer
  - Optimizer: Adam
  - Training: With `EarlyStopping`
- **Output**: 
  - Saved model as `power_forecast_model.h5`

---

## 📁 Project Structure

project/
├── intro-to-kaggle-in-se-project.ipynb # Model training notebook
├── power_forecast_model.h5 # Trained LSTM model
└── web-app/
├── app.py # Flask backend
├── templates/
│ └── index.html # Web UI for prediction
└── static/
└── style.css # Optional styling


---

## 🌐 Flask Web Application

The web app allows users to:
- Enter the past 5 days of power and pressure data
- Get predictions for the next 5 days
- View the results in a clean, minimal UI

### How it works:
1. `app.py` loads the `.h5` model
2. User inputs data via form (`index.html`)
3. Data is scaled, reshaped, and passed to the model
4. Output is rendered on the same page

---

## 🚀 Running the Project

### 🧠 Train the Model (Kaggle Notebook)
1. Open `intro-to-kaggle-in-se-project.ipynb`
2. Run all cells
3. This will generate `power_forecast_model.h5`

## 🌐 Live Deployment

The web app is hosted on **Render** and is live at:

🔗 [Power Forecast Web App](https://render-flask-deploy-1.onrender.com/predict)

---

## 🚀 Deployment Details

- **Platform**: [Render](https://dashboard.render.com)
- **Live App**: [https://render-flask-deploy-1.onrender.com/predict](https://render-flask-deploy-1.onrender.com/predict)
- **GitHub Repository**: [Dhruv-Singla/render-flask-deploy](https://github.com/Dhruv-Singla/render-flask-deploy)
- **Build Command**: `pip install -r requirements.txt`
- **Start Command**: `python app.py`

Ensure the `.h5` model is included in the repository and the environment is properly configured.



---

## 🛠️ Deployment Steps

To make the AI model accessible through a web interface, we deployed the project using GitHub and Render. Here's how:

1. **Prepare the Flask App**
   - Created a `Flask` project with:
     - `app.py`: Python server script to load `.h5` model and handle prediction requests
     - `templates/index.html`: Frontend form to take input and show output
     - `static/`: Folder for styling (CSS)
     - Trained `.h5` model included in the project folder

2. **Push to GitHub**
   - The complete codebase was pushed to a public GitHub repository:  
     🔗 [Dhruv-Singla/render-flask-deploy](https://github.com/Dhruv-Singla/render-flask-deploy)

3. **Deploy via Render**
   - Logged in to [Render Dashboard](https://dashboard.render.com)
   - Clicked on **"New Web Service"**
   - Connected the GitHub repository
   - Set the build and start commands:
     - **Build Command**: `pip install -r requirements.txt`
     - **Start Command**: `python app.py`
   - Selected a free instance for deployment
   - Render automatically detected the Flask app and deployed it to:
     🔗 [https://render-flask-deploy-1.onrender.com/predict](https://render-flask-deploy-1.onrender.com/predict)



---

📚 References
Keras LSTM Documentation

Flask Web Framework

Dataset: Custom Excel file from Kaggle input directory



This project was developed by Aayush Kalia, Dhruv Singla and Akashdeep Singh as part of an academic project.