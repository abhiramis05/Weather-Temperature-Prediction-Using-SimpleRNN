# Weather-Temperature-Prediction-Using-SimpleRNN
# 🌤️ Weather Temperature Prediction Using SimpleRNN

## 📌 Project Overview

This project uses a **SimpleRNN (Recurrent Neural Network)** to predict the next day's temperature using past weather data.

The model learns patterns from the previous **7 days** of weather information, including:

* Temperature
* Humidity
* Wind Speed

The project also evaluates the model using **RMSE, MAE, and R² Score** and forecasts the temperature for the **next 7 days**.

---

## 🎯 Objective

The main objective of this project is to:

* Prepare and preprocess weather data.
* Analyze temperature trends over time.
* Create time-series sequences using previous 7 days.
* Build a SimpleRNN model using TensorFlow/Keras.
* Train and validate the model.
* Evaluate the model's prediction performance.
* Forecast temperature for the next 7 days.

---

## 📊 Dataset

The project uses a **Daily Weather Dataset**.

### Features Used

| Feature     | Description       |
| ----------- | ----------------- |
| Temperature | Daily temperature |
| Humidity    | Daily humidity    |
| Wind Speed  | Daily wind speed  |

### Target Variable

**Temperature of the next day**

The previous 7 days are used as input to predict the temperature of the following day.

---

## 🔄 Project Workflow

```text
Load Dataset
     ↓
Explore Dataset
     ↓
Check Missing Values
     ↓
Handle Missing Values
     ↓
Select Features
     ↓
Normalize Data
     ↓
Create 7-Day Sequences
     ↓
Train / Validation / Test Split
     ↓
Build SimpleRNN Model
     ↓
Train Model
     ↓
Evaluate Model
     ↓
Plot Actual vs Predicted
     ↓
Forecast Next 7 Days
```

---

## 🛠️ Technologies Used

* Python
* NumPy
* Pandas
* Matplotlib
* Scikit-learn
* TensorFlow
* Keras
* SimpleRNN

---

## 🧹 Data Preprocessing

The selected weather features are extracted from the dataset.

Missing values are handled using interpolation.

The data is then normalized using **MinMaxScaler** so that the input values are brought into a suitable range for neural network training.

---

## 🔢 Sequence Creation

The model uses the previous **7 days** of weather data to predict the next day's temperature.

For example:

```text
Days 1–7  → Predict Day 8
Days 2–8  → Predict Day 9
Days 3–9  → Predict Day 10
```

Each sequence contains:

```text
7 days × 3 features
```

The three features are:

```text
Temperature
Humidity
Wind Speed
```

---

## 📚 Data Splitting

The data is divided chronologically into:

* **70% Training Data**
* **15% Validation Data**
* **15% Testing Data**

The order of the data is maintained because this is a time-series prediction problem.

---

## 🧠 SimpleRNN Model

The model contains:

```text
Input Layer
     ↓
SimpleRNN (32 units)
     ↓
Dropout (0.2)
     ↓
Dense Output Layer
```

The model is compiled using:

* **Optimizer:** Adam
* **Loss Function:** Mean Squared Error (MSE)
* **Metric:** Mean Absolute Error (MAE)

---

## 📈 Model Training

The model is trained using:

* **Epochs:** 50
* **Batch Size:** 32
* **Validation Data:** Validation dataset

Training and validation loss are plotted to observe the model's learning performance.

---

## 📏 Model Evaluation

The trained model is evaluated on the test dataset using:

### RMSE

Root Mean Squared Error measures the difference between actual and predicted temperatures.

### MAE

Mean Absolute Error shows the average absolute prediction error.

### R² Score

R² Score indicates how well the model explains the variation in temperature.

---

## 📊 Visualization

The project includes:

### Temperature Trend

Shows how temperature changes over time.

### Training vs Validation Loss

Shows the model's learning performance during training.

### Actual vs Predicted Temperature

Compares the actual temperature with the temperature predicted by the model.

### 7-Day Forecast

Shows the predicted temperature for the next 7 days.

---

## 🔮 7-Day Temperature Forecast

After training, the model is used to forecast the temperature for the next **7 days**.

The forecasting process uses the most recent 7-day sequence and predicts one day at a time.

```text
Last 7 Days
     ↓
Predict Day 1
     ↓
Update Sequence
     ↓
Predict Day 2
     ↓
Update Sequence
     ↓
...
     ↓
Predict Day 7
```

For future forecasting, the latest available humidity and wind-speed values are kept constant because future values for these variables are not provided in the assignment.

---

## 📁 Project Structure

```text
Weather-Temperature-Prediction/
│
├── Weather_Temperature_Prediction.ipynb
├── README.md
└── dataset.csv
```

---

## ✅ Results

The model's performance is evaluated using:

```text
RMSE
MAE
R² Score
```

The final results depend on the dataset and the training process.

---

## 🚀 Conclusion

This project demonstrates how a **Simple Recurrent Neural Network (SimpleRNN)** can be used for weather temperature forecasting.

By using the previous 7 days of temperature, humidity, and wind speed, the model learns temporal patterns and predicts future temperature values.

The project also demonstrates the complete workflow of a time-series deep learning problem, from data preprocessing and sequence creation to model training, evaluation, and future forecasting.
