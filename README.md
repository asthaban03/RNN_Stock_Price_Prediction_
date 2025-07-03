## **Objective**

Given the stock prices of Amazon, Google, IBM, and Microsoft for a set number of days, predict the stock price of these companies after that window.

## Table of Contents
* [General Info](#general-information)
* [Technologies Used](#technologies-used)
* [Conclusions](#conclusions)
* [Acknowledgements](#acknowledgements)

<!-- You can include any other section that is pertinent to your problem -->

## General Information
- Provide general information about your project here.
- What is the background of your project?
- What is the business problem that your project is trying to solve?
- What is the dataset that is being used?

## General Information

The objective of this assignment is to try and predict the stock prices using historical data from four companies IBM (IBM), Google (GOOGL), Amazon (AMZN), and Microsoft (MSFT).
We use four different companies because they belong to the same sector: Technology. Using data from all four companies may improve the performance of the model. This way, we can capture the broader market sentiment.

## Conclusions
**Model Training approach and Results**


### Approach
The data analysis was conducted with a training and validation split of 80:20
#### Frequency distribution
The frequency distribution plot was used to understand the trading volume for the four stocks. This helped to understand the spread of the various stocks in terms of volume/business thus giving insight on the stock profitability, volatility, long term stocks etc.

#### Simple RNN model
We built a simple RNN model to have a basic understanding of the dataset before exploring more complex variants like GRU. We used output shape of (None, 64) and 4480 parameters. We used a Dense layer in Layer2 with 65 parameters and output shape of (None, 64). One neuron was used for binary classification.

#### GRU Model
We built a GRU-based neural network and performed hyperparameter tuning by adjusting units, activation functions, dropout values, and learning rates. After testing different combinations, the best performance came from the model with 128 GRU units, ReLU activation, 0.3 dropout, and a 0.001 learning rate.

### Data Insights
#### The Frequency distribution of volume shows that, for all stocks:
- There is low to moderate volume on most of the trading days
- There are some outliers i.e. very high volumes but that is rare.
- For Amazon, majority of days see low volume. Very few unusually high volume.
- IBM has more uniform spread compared to other stocks.
- Microsoft is the most variably traded stock.
- The trend analysis of the stocks over the years shows that:
- Amazon and Google has a strong upward trend over the years, this shows a strong performance by these stocks.
- Amazon is bit volatile due to some sharp fluctuations whereas Google is less volatile and shows steady growth.
- IBM has a very slow growth till 2013 and post that showing a decline. This is under-performance compared to peers.
- Microsoft shows slow and steady growth with less volatility.

#### Analysis with the Simple RNN model
- We got a Mean Square Error (MSE) of 69.03 which suggests that on average performance, the lower is better.
- Root Mean Squared Error (RMSE): 8.30 unit implies the model predictions deviate from actual values by approximately 8.30 units on average.
- R-squared : 0.9988 means model explains 99.86% of the variance in the target.This is outstanding and suggests excellent predictive power and tight fitting to the data.
- With the test data, the MSE is 69.0 which is similar as the training data. The RMSE still remains around the same i.e. ~7.5 and R-Squared is again excellent99.89%.

#### Analysis with the GRU model
- A Mean Squared Error (MSE) loss of 0.0062 means that, on average, the squared difference between your model’s predictions and the actual target values is 0.0060. This is a very small value, suggesting your model's predictions are extremely close to the actual values.
- An RMSE of 0.0806 means Predictions are very close to actual values. The average error is ~8% of the total range (since 0.0806 out of [0–1]).This is excellent performance for many machine learning tasks.

### Final Takeaways from above analysis:
- Investors favor AMAZON and GOOGLE for long-term capital appreciation.
- MICROSOFT demonstrates reliable late-stage growth, ideal for stable portfolios.
- IBM lags behind — shows a decline or stagnation requiring relook into investment strategies.
- We get good insight into few aspects using simple RNN but better results are provided with GRU with hyper-tuning.RMSE values across companies confirmed that the model can generalize decently across different datasets when trained properly.


## Technologies Used
- numpy version: 1.26.4
- pandas version: 2.2.2
- seaborn version: 0.13.2
- matplotlib version: 3.10.0
- PIL version: 11.1.0
- tensorflow version: 2.18.0
- keras version: 3.8.0
- sklearn version: 1.6.1


<!-- As the libraries versions keep on changing, it is recommended to mention the version of library used in this project -->

## Acknowledgements
Give credit here.
- This is an assignment from upgrad.

## Contact
Created by [@chinmayajeet @asthabansal] - feel free to contact us!


<!-- Optional -->
<!-- ## License -->
<!-- This project is open source and available under the [... License](). -->

<!-- You don't have to include all sections - just the one's relevant to your project -->
