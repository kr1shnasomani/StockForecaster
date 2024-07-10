# Stock-Price-Predictor

1. Import the following libraries:
   - pandas
   - NumPy
   - Matplotlib
   - TensorFlow
   - scikit-learn
   - searborn

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
