# 🌦️ Weather Prediction using LSTM

This project implements a Recurrent Neural Network (RNN) using **Long Short-Term Memory (LSTM)** units to predict future weather conditions based on historical data. Specifically, it focuses on forecasting the daily **maximum temperature** (`temp_max`) using univariate time-series analysis.

## 📂 Dataset
The model uses the **Seattle Weather Dataset** (`seattle-weather.csv`), which contains daily records of:
* **Date**
* **Precipitation**
* **Temp_max** (Target Variable)
* **Temp_min**
* **Wind**
* **Weather Type** (drizzle, rain, sun, etc.)

*Note: The current implementation utilizes the `temp_max` column to train the model in a univariate fashion.*

## 🛠️ Technologies & Libraries
* **Python 3**
* **TensorFlow / Keras** (for building the LSTM model)
* **Pandas** (for data manipulation)
* **NumPy** (for array operations and reshaping)
* **Matplotlib & Seaborn** (for visualizing loss and predictions)

## 🧠 Model Architecture
The model is a stacked LSTM network designed to capture temporal dependencies in the weather data:
1.  **Input Layer**: Accepts sequences of 10 previous days (Window Size = 10).
2.  **LSTM Layers**: Four stacked LSTM layers with 50 units each. The first three return sequences to feed into the subsequent layers.
3.  **Regularization**: Dropout layers (rate = 0.2) are added after each LSTM layer to prevent overfitting.
4.  **Output Layer**: A Dense layer with 1 unit to predict the next day's maximum temperature.
5.  **Optimizer**: Adam.
6.  **Loss Function**: Mean Squared Error (MSE).

## 📊 Performance
The model is trained over **100 epochs** with a batch size of 32. Training progress is monitored using:
* **Loss vs. Validation Loss**: Visualized to ensure the model converges and to check for overfitting.
* **Prediction**: The model generates predictions for training, validation, and testing sets for visual comparison against actual data.

## 🚀 How to Run
1.  Clone this repository:
    ```bash
    git clone https://github.com/VirajsNexus/Weather-Prediction-LSTM.git
    ```
2.  Navigate into the project folder:
    ```bash
    cd Weather-Prediction-LSTM
    ```
3.  Install the required dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn tensorflow
    ```
4.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook weather-prediction-using-LSTM.ipynb
    ```

## 📈 Future Improvements
* Incorporate multivariate time-series analysis (using precipitation, wind, and min temp) to improve accuracy.
* Implement Bidirectional LSTMs or GRU units for comparison.
* Hyperparameter tuning for window size and unit count.

## 🤝 Contributing
Contributions, issues, and feature requests are welcome!

## 📜 License
[MIT](https://github.com/VirajsNexus/Weather-Prediction-LSTM/blob/main/LICENSE)
