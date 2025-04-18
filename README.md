# 📈 Google Stock Price Prediction using LSTM

This project demonstrates the use of Long Short-Term Memory (LSTM) neural networks to predict the next day's closing price of Google (GOOG) stock based on historical data. It showcases how deep learning can be applied to financial time series forecasting.

---

## 📌 Problem Statement

Stock price forecasting is a challenging task due to the volatile and non-linear behavior of the stock market. The goal of this project is to use LSTM networks to capture temporal dependencies and accurately predict future prices, enabling investors to make better decisions.

---

## 🗂️ Repository Structure

├── stock_price_prediction.ipynb # Jupyter notebook with complete code and plots 
├── README.md # Project documentation


---

## 🛠️ Tools & Libraries

- **Language**: Python 3  
- **Notebook**: Jupyter Notebook  
- **Libraries**:  
  - Data: `NumPy`, `Pandas`, `yfinance`  
  - Preprocessing & Evaluation: `scikit-learn`  
  - Visualization: `Matplotlib`  
  - Deep Learning: `TensorFlow`, `Keras`

---

## 🧪 Methodology

### 📥 Data Collection
- Fetched Google stock data from Yahoo Finance using `yfinance`.
- Time period: **2010-01-01 to 2025-01-01**
- Feature used: `'Close'` price

### ⚙️ Data Preprocessing
- Scaled the closing prices using `MinMaxScaler` (range 0 to 1)
- Created a dataset of sequences where each input contains 60 days of data to predict the 61st day's closing price
- Split into training (80%) and testing (20%) datasets without shuffling to retain temporal order

### 🧠 Model Architecture
- **Input shape**: (60 timesteps, 1 feature)
- **Model Layers**:
  - LSTM layer with 50 units, return sequences: `True`
  - Dropout layer with rate 0.2
  - Second LSTM layer with 50 units, return sequences: `False`
  - Dropout layer with rate 0.2
  - Dense output layer with 1 neuron
- **Loss Function**: Mean Squared Error
- **Optimizer**: Adam (learning rate = 0.001)
- **Training**: 10 epochs, batch size 32, validated on test data

---

## 📊 Results & Evaluation

### 📈 Visualization
- The model’s predicted prices closely followed the actual prices in the test set
- Captured general trend and direction of price movement

### 📏 Performance Metric
- **Root Mean Squared Error (RMSE)**: **~8.18**
- This indicates reasonably good accuracy for a univariate model using only closing prices

---

## 🚀 How to Run the Project

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-username/stock-price-prediction-lstm.git
   cd stock-price-prediction-lstm

