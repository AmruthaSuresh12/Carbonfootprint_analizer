# 🌱 GreenPulse: Real-Time Carbon Intelligence Platform

GreenPulse is a real-time carbon intelligence platform designed to monitor server fleet power consumption, detect operational anomalies, simulate carbon-aware workload shifting, and predict future emissions using machine learning.

The platform is designed to help green-data-center operators visualize, mitigate, and forecast their hardware carbon footprint.


## 📊 Dataset Attribution

This project is trained and simulated using the **official server telemetry dataset provided by Lenovo**. The dataset contains high-frequency power usage data across different server hardware configurations, enabling highly realistic simulations and machine learning forecasts.

## ✨ Key Features

* **⚡ Real-Time Fleet Dashboard**: A unified Streamlit interface displaying current fleet power usage (Watts), cumulative carbon emissions (kg CO₂), and active anomalies.
* **🟢 Real-Time Telemetry Simulator**: Streams live server telemetry data into MongoDB, mimicking live server metrics and periodically injecting high-wattage power spikes.
* **🔍 AI Anomaly Detection**: Monitors incoming telemetry to detect and log power spikes, warning operators of inefficient hardware behavior.
* **🔄 Carbon-Aware Workload Shifting**: Simulates shifting server workloads from high-emitting nodes to cleaner, low-emission servers to optimize carbon output.
* **🤖 Emission Prediction Model**: A Random Forest Regressor trained on the official Lenovo dataset to predict server emissions based on temporal patterns and power lags.
* **📊 Server Deep-Dives**: Detailed granular charts showing historical metrics, specific server performance, and historical anomalies.

## 🛠️ Tech Stack

* **Frontend/Dashboard**: Streamlit, Plotly
* **Database**: MongoDB (PyMongo)
* **Data Processing & ML**: Pandas, Numpy, Scikit-Learn
* **Runtime**: Python 3.13+

## 📁 Project Structure

greenpulse/
├── greenpulse/                # Core application source
│   ├── database/              # MongoDB connection wrappers
│   ├── features/              # Analysis pipelines (Anomaly, Prediction, Shifting)
│   ├── pages/                 # Streamlit dashboard pages
│   ├── pipeline/              # Ingestion and cleaning pipelines
│   ├── alerts.py              # Alarm thresholds and notification system
│   ├── app.py                 # Streamlit main entry point
│   ├── config.py              # Constant configurations and DB URI
│   ├── dataset.csv            # Copy of the raw telemetry dataset
│   └── requirements.txt       # Project python dependencies
├── dataset.csv                # Root dataset file (Lenovo)
├── simulator.py               # Live telemetry generator
└── train_model.py             # Offline ML model training script
