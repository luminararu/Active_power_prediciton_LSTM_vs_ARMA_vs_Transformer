# Active Power Prediction using LSTM, ARMA, and Transformer

## 📌 Project Overview

This project focuses on predicting the electrical energy consumption of a household using time series forecasting techniques. The main objective is to compare the performance of three different models:

* **LSTM (Long Short-Term Memory)**
* **ARMA (AutoRegressive Moving Average)**
* **Transformer-based Neural Network**

The dataset originally contains measurements recorded every minute. In this project, the data is preprocessed and aggregated to **hourly resolution** for better modeling and efficiency.

---

## 📊 Dataset Description

The dataset contains measurements of electric power consumption in one household located in **Sceaux, France**, collected over nearly **4 years (December 2006 – November 2010)**.

### General Characteristics

* **Type:** Multivariate Time Series
* **Domain:** Physics and Chemistry
* **Associated Tasks:** Regression, Clustering
* **Feature Type:** Real-valued
* **Instances:** 2,075,259
* **Features:** 9
* **Sampling Rate:** 1 minute (converted to 1 hour)
* **Missing Values:** Yes (~1.25%)

---

## 📈 Dataset Information

The archive contains 2,075,259 measurements gathered over a period of 47 months.

### Notes

1. The following formula represents the active energy consumed every minute by equipment not measured in sub-meterings:

```
(global_active_power * 1000 / 60) - sub_metering_1 - sub_metering_2 - sub_metering_3
```

2. The dataset contains missing values. All timestamps are present, but some measurement values are missing and represented by empty fields.

---

## 📋 Variables

| Variable Name         | Type        | Description                       | Missing Values |
| --------------------- | ----------- | --------------------------------- | -------------- |
| Date                  | Date        | Measurement date                  | No             |
| Time                  | Categorical | Measurement time                  | No             |
| Global_active_power   | Continuous  | Global active power               | No             |
| Global_reactive_power | Continuous  | Global reactive power             | No             |
| Voltage               | Continuous  | Voltage level                     | No             |
| Global_intensity      | Continuous  | Global current intensity          | No             |
| Sub_metering_1        | Continuous  | Kitchen energy consumption        | No             |
| Sub_metering_2        | Continuous  | Laundry room energy consumption   | No             |
| Sub_metering_3        | Continuous  | Climate system energy consumption | No             |

---

## ⚙️ Data Preprocessing

The following preprocessing steps are applied:

* Handling missing values (interpolation / removal)
* Converting minute-level data to hourly averages
* Normalization / standardization
* Time series windowing
* Train / validation / test split

---

## 🧠 Models Used

### 1. LSTM (Long Short-Term Memory)

LSTM networks are used to model long-term dependencies in time series data. They are suitable for capturing temporal patterns in energy consumption.

### 2. ARMA

ARMA is a traditional statistical model that combines autoregressive and moving average components. It serves as a baseline for comparison.

### 3. Transformer

The Transformer model uses self-attention mechanisms to capture global dependencies in the time series, enabling efficient parallel processing and long-range modeling.

---

## 📐 Model Architecture

* Input: Time windows of historical energy consumption
* Output: Predicted future energy values
* Loss Function: Mean Squared Error (MSE)
* Optimizer: Adam (for deep learning models)

---

## 📁 Project Structure

```
Active_power_prediction/
│
├── data/           # Raw and processed datasets
├── notebooks/      # Jupyter notebooks for exploration
├── src/            # Source code
│   ├── preprocessing/
│   ├── models/
│   └── evaluation/
├── results/        # Evaluation results and plots
├── requirements.txt
└── README.md
```

---

## 🚀 Installation

Clone the repository:

```bash
git clone https://github.com/luminararu/Active_power_prediciton_LSTM_vs_ARMA_vs_Transformer.git
cd Active_power_prediciton_LSTM_vs_ARMA_vs_Transformer
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## ▶️ Usage

Run preprocessing:

```bash
python src/preprocessing/preprocess.py
```

Train models:

```bash
python src/models/train_lstm.py
python src/models/train_arma.py
python src/models/train_transformer.py
```

Evaluate models:

```bash
python src/evaluation/evaluate.py
```

---

## 📊 Evaluation Metrics

The models are evaluated using:

* Mean Squared Error (MSE)
* Root Mean Squared Error (RMSE)
* Mean Absolute Error (MAE)
* R² Score

---

## 📌 Results

The performance of each model is compared in terms of prediction accuracy and computational efficiency. Detailed results and visualizations are available in the `results/` directory.

---

## 🧩 Future Work

* Hyperparameter optimization
* Multi-step forecasting
* Inclusion of external factors (weather, holidays)
* Real-time prediction system

---

## 👤 Author

**Lumînăraru Ionuț-Andrei**

---

## 📄 License

This project is intended for academic and educational purposes.
