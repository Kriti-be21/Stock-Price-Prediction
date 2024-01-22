# Stock-Price-Prediction

1. **Data Retrieval:**
   - The project begins by importing necessary libraries and downloading the required datasets using Quandl.
   - Historic stock prices for MSFT are retrieved from Quandl's WIKI database using web Scrapping.

2. **Data Preprocessing:**
   - Stock prices are structured into a DataFrame with the date, ticker, and adjusted closing prices.
   - The data is pivoted to have tickers as columns, dates as rows, and adjusted closing prices as values.
   - The resulting DataFrame is saved to a pickle file for future use.

3. **Sentiment Analysis:**
   - Textual data related to Microsoft (MSFT) is retrieved from the created pickle file.
   - The text is preprocessed by splitting it into sentences and performing sentiment analysis using the VADER (Valence Aware Dictionary and sEntiment Reasoner) sentiment analysis tool.
   - The sentiment scores are aggregated to create a single sentiment score for each day.

4. **Time Series and Sentiment Integration:**
   - The sentiment scores are merged with the stock price data based on the date.
   - The combined dataset is resampled to a daily frequency, and missing values are filled using forward filling.

5. **Feature Engineering:**
   - The data is split into training and testing sets, and features are created for time series analysis with a specified look-back window.
   - Features include the original time series of Microsoft stock prices and sentiment analysis scores.

6. **Model Building:**
   - A Sequential model using LSTM layers is constructed for time series prediction.
   - The model is trained using the combined features and target variable (MSFT stock prices) with Adam optimizer and Mean Squared Error loss.
   - Early stopping is applied to prevent overfitting.

7. **Model Evaluation:**
   - The trained model is evaluated on both the training and testing datasets.
   - Mean Absolute Error (MAE) and Root Mean Squared Error (RMSE) are calculated and printed to assess the model's performance.

8. **Visualization:**
   - Plots are generated to visualize the training and validation loss during model training.
   - Another plot visualizes the actual and predicted MSFT stock prices for both the training and testing periods, incorporating sentiment analysis.

9. **Conclusion:**
   - The project concludes by providing insights into how well the LSTM model, combined with sentiment analysis features, performs in predicting MSFT stock prices.
   - The visualization provides a comparative view of actual and predicted prices, allowing for an assessment of the model's accuracy.
