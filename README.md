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

* 📂 **`greenpulse/`** — Root repository directory
  * 📂 **`greenpulse/`** — Main application source code
    * 📂 **`database/`** — MongoDB interface and configuration wrappers
    * 📂 **`features/`** — Analysis modules (anomaly detection, predictive modeling, shifting)
    * 📂 **`pages/`** — Streamlit dashboard sub-pages and charts
    * 📂 **`pipeline/`** — Data ingestion and cleaning pipeline
    * 📄 **`alerts.py`** — Alert warning thresholds and logic
    * 📄 **`app.py`** — Streamlit frontend web app entry point
    * 📄 **`config.py`** — Constant configurations and DB parameters
    * 📄 **`dataset.csv`** — Cleaned copy of server telemetry dataset
    * 📄 **`requirements.txt`** — Core package dependencies list
  * 📄 **`dataset.csv`** — Official raw fleet telemetry dataset (provided by Lenovo)
  * 📄 **`simulator.py`** — Live real-time server telemetry streamer
  * 📄 **`train_model.py`** — Offline machine learning training pipeline
