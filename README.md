### Options Pricing using Deep Learning - Benchmarked against Black Scholes

## LSTM Model

This model uses a stacked Long Short Term Memory (LSTM) architecture with dense layers. The LSTM model structure is well-suited for time series data.

The input layer contains the inputs lookback and number of features.

The architecture is as follows:

1. The first LSTM layer contains 64 LSTM units with return sequences enabled, allowing it to output the full sequence.
2. A dropout layer with a rate of 0.2 follows to prevent overfitting.
3. The second LSTM layer contains 32 LSTM units and doesn't return sequences, outputting only the final state.
4. Another dropout layer with a rate of 0.2 is applied.
5. A dense layer with 16 units and ReLU activation follows, acting as a fully connected layer.
6. The final output layer is a dense layer with a single unit, producing the predicted option price.

The model uses the Adam optimizer with a learning rate of 0.001 and is compiled with mean squared error as the loss function.

This architecture allows the model to capture both long-term dependencies in the time series data through the LSTM layers and make a final prediction through the dense layers.

## Selected Results

![image](https://github.com/user-attachments/assets/f0e9d990-d6a9-4d00-93d8-da6ebb432a23)

![image](https://github.com/user-attachments/assets/8ef7c4f5-3297-4362-9862-a2cd80dc3fd0)

### Interpretation

1. Deep Learning RMSE: 0.1600
   - This measures the standard deviation of the residuals (prediction errors) for the deep learning model.
   - In the context of option prices, this suggests that on average, the model's predictions deviate from the actual market prices by about $0.16.

2. Black-Scholes RMSE: 1.0803
   - This measures the standard deviation of the residuals for the Black-Scholes model.
   - It indicates that, on average, the Black-Scholes prices deviate from the actual market prices by about $1.08.

3. Deep Learning MAPE: 0.0650%
   - This shows the Mean Absolute Percentage Error for the deep learning model.
   - A 0.065% error suggests that, on average, the model's predictions deviate from the actual market prices by about 0.065% in either direction.

4. Black-Scholes MAPE: 3.7338%
   - This shows the Mean Absolute Percentage Error for the Black-Scholes model.
   - A 3.73% error indicates that, on average, the Black-Scholes prices deviate from the actual market prices by about 3.73% in either direction.

Interpretation:
- The deep learning model's performance significantly outperforms the Black-Scholes model using both RMSE and MAPE metrics.
- The deep learning model shows much lower RMSE compared to Black-Scholes (0.16 vs 1.08), suggesting it provides substantially more accurate predictions on average.
- The deep learning model's dramatically lower MAPE (0.065% vs 3.73%) indicates it has far better relative accuracy across different price ranges compared to Black-Scholes.
- Overall, these results show that the deep learning model performs remarkably better than the Black-Scholes model in both RMSE and MAPE metrics.
- This suggests that the deep learning approach has significant potential to improve upon traditional option pricing models, particularly in capturing market dynamics that may not be fully accounted for in the Black-Scholes model.
