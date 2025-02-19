# AI-Rent-Predictions
A repository of the work done for my Deep Learning class's final project.

## Dataset
Originally, I was going to use a dataset from the Research & Analytics Group at the Atlanta Regional Commission using information published by the US Census Bureau. This did not work due to the Research & Analytics Group only posting complete data for the years 2019, 2020, and 2021.

I was advised by my profressor to use a different dataset, one encapsulating a larger timespan. After researching and consulting my professor, this project utilized a dataset collected from [RentData.org](https://www.rentdata.org). This website is an independent organization not affiliated with any governmental agency. The website features interactive maps and rent market analysis for public use based on the Fair Market Rent rate published by the Department of Housing and Urban Development. 

Information from this website was manually collected into a CSV file that model would be able to read. The collected information featured the average rent price for a studio, 1-bedroom, 2-bedroom, 3-bedroom, and 4-bedroom apartment for a given year in a county.

Below is an example of the format for an entry in the dataset.

![image](https://github.com/user-attachments/assets/fb8218a8-2738-41ba-bc1c-a50a89c40233)

## AI Model
This project consisted of creating and testing a multi-layered perceptron and Long-Short Term Memory (LSTM) model. These models were then compared to determine the most efficient and accurate model. 

The multi-layered perceptron consisted of an input and output layer with two hidden layers using the Relu activation function. Each hidden layer was also followed by a Normalization layer. 

![image](https://github.com/user-attachments/assets/0356a7c9-a643-4064-afb5-bbffab7ff7a9)

The LSTM model was comprised of four LSTM layers, each with fifty neurons. Like the multi-layered perceptron a Normalization layer followed each LSTM layer to standardize the output. 

![image](https://github.com/user-attachments/assets/c7627fde-2dec-4ded-803a-db0521ff8bfb)

Both models were trained using 32 batches over 100 epochs.

## Evaluation Metrics
The models both utilized a mean absolute error (MAE) as their accuracy metrics. The MAE metric was chosen due to its resistance to outliers. Due to the nature of rent prices in Georgia, the dataset included extreme outliers that could not be excluded due to representing actual values. An MAE metric helped ensure these outliers were still coutned without skewing the model.

The results of the models were measure using the Mean Absolute Percentage Error (MAPE), which is a percentage equivalent of the MAE. 

## Results
The predicted rent prices for the year 2024 can be found in the [Project Predictions.xlsx](https://github.com/TFitzgerald1/AI-Rent-Predictions/blob/01e488facf476fc8460e9c6ea60e8cfa5c6fee0f/Project%20Predictions.xlsx).

Further explanation of the results of the project are discuessed in the [Final Report](https://github.com/TFitzgerald1/AI-Rent-Predictions/blob/693f20a2d7704bb16bb3bf3741541134989aec39/Project%20Predictions.xlsx). Both models would start with a high MAE value but quickly converge to an MAE of approximately $49 (for perceptron) and $39-$44 (for LSTM).

![Untitled](https://github.com/user-attachments/assets/2ee8061a-4dea-4a03-b717-b30dc95a01a2)

![Untitled-1](https://github.com/user-attachments/assets/c35f3b37-fd89-4319-b754-2e29456e60e9)

![Untitled](https://github.com/user-attachments/assets/8f13bb3d-71b7-462e-88df-7b7a138f08e7)
