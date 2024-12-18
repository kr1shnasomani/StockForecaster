<h1 align="center">StockForecaster</h1>
The predictor predicts stock prices using LSTM networks. It processes historical stock data, scales it, and splits it into training and testing sets. After training the model, it predicts future stock prices for the next 30 days and visualizes the predictions alongside actual data. 

## Execution Guide:
1. Run the following command line in the terminal:
   ```
   pip install pandas matplotlib numpy tensorflow seaborn scikit-learn
   ```

2. Enter the company's name whose stock prediction you want to see. Now go to 'https://finance.yahoo.com' > search for the company > click on 'Historical Data' > click on 'Download'. The CSV file containing the information of the stock gets downloaded. Copy the path of the CSV file and paste it in the code.

3. Code in In[5] outputs the graph of the lifetime price data of the company.
   
   ![image](https://github.com/kr1shnasomani/Stock-Price-Predictor/assets/141762169/5da9e5db-5d28-4087-ae09-2d87fda65637)

4. Code in In[6] shows the information of the latest closing price of the stock. It outputs latest day's high & low, opening & closing and 52-week high & low

5. Code in In[7] outputs the graph of the lifetime volume data of the company.

   ![image](https://github.com/kr1shnasomani/Stock-Price-Predictor/assets/141762169/c1a2d69c-c02a-40e4-8146-4373e99780fa)

6. Code in In[8] splits the data into training and testing, scales the dataset, prepares training and testing data, builds the LSTM model, compiles the model and in the end trains the model

7. Code in In[7] outputs the graph of the prediction of the stock price for the next 30 days.

   ![image](https://github.com/kr1shnasomani/Stock-Price-Predictor/assets/141762169/9d1cec22-0cd2-4f2a-8b2d-ebc96c0e6990)

8. Code in In[8] prints the the predicted closing price for the next 30 days.

   ![image](https://github.com/user-attachments/assets/03a62180-55d2-4776-a4b3-fe6c133fe6b1)

## Overview:
The code implements a **stock price prediction** model for **Rail Vikas Nigam Ltd. (RVNL)** using a **Long Short-Term Memory (LSTM)** model, a type of recurrent neural network (RNN) commonly used for time-series forecasting tasks like stock price prediction. Here's an overview of the process:

1. **Data Preprocessing:**
   - **Importing Data:** The stock price data for RVNL is loaded from a CSV file using **Pandas**. The data contains columns like `Date`, `Open`, `High`, `Low`, `Close`, and `Volume`.
   - **Date Conversion:** The `Date` column is converted to `datetime` type for easier manipulation.
   - **Plotting:** The closing prices (`Close`) and trading volume (`Volume`) are plotted over time using **Matplotlib**.

2. **Additional Insights:**
The script calculates and prints the **highest**, **lowest**, **opening**, and **closing prices** for the most recent trading day. It also calculates the **52-week high** and **52-week low** for the stock.

3. **Data Splitting:**
The data is split into **training** and **test sets**:
     - **Training set**: 80% of the data is used for training the model.
     - **Test set**: The remaining 20% is used for testing the model's performance.

4. **Scaling the Data:**
**MinMaxScaler** from **sklearn** is used to scale the stock prices between 0 and 1, as LSTM models perform better with normalized data.

5. **Preparing Data for LSTM:**
   - **Training Data:** 
     - Sequences of 60 days of data are used as input (`x_train`), and the stock price on the next day (`y_train`) is used as the target.
     - The input data (`x_train`) is reshaped to 3D (samples, timesteps, features) for LSTM processing.
   - **Testing Data:** Similar preprocessing is done for the test data (`x_test`).

6. **Building the LSTM Model:**
   - The LSTM model consists of two LSTM layers with 64 units each, with **Dropout** layers to prevent overfitting.
   - A **Dense layer** is added to output the predicted closing price.
   - The model is compiled using the **Adam optimizer** and **Mean Squared Error (MSE)** as the loss function.
   - The model is trained for 50 epochs.

7. **Model Training:**
The model is trained on the `x_train` and `y_train` data, and the loss during training is displayed. The model learns to predict the stock price based on the previous 60 days.

8. **Making Predictions:**
   - After training, predictions are made on the test set (`x_test`), and the results are **inverse-transformed** to get the original price values.
   - **Future Predictions** for the next 30 days are made using the last 60 days of scaled data, simulating future stock price movements.

9. **Plotting Results:**
   - The **actual and predicted** closing prices for both the training and testing periods are plotted for visualization.
   - The predicted stock prices for the next 30 business days are displayed, showing the expected trend in the stock price.

10. **Predicted Stock Prices for the Next 30 Days:**
The model predicts the stock closing prices for the next 30 business days (as shown in the output), providing a potential future trend for the stock.
