## Algorithmic Trading Bot

The purpose of this project is to create an algorithmic trading bot that learns and adapts to new data and evolving markets. The goal is to implement an algorithmic trading strategy that uses machine learning to automate the trade decisions, adjust the input parameters to optimize the trading algorithm, and train a new model to compare its performance to the baseline model. 

---

## Technologies

This project will be coded in Python using a Jupyter notebook. We will use multiple libraries and dependencies, including pandas, matplotlib, and sklearn. 

---

## Usage

The first step is to establish a baseline performance for the trading algorithm. After creating the dataframe, I used short and long window Simple Moving Average (SMA) values to generate trading signals. The short window was set to 4 days, and the long window was set to 100 days. I used these two windows to generate their respective SMA values, then added a column to the dataframe that determines whether the bot should buy long on a stock or sell short. I added another column to generate the returns for the algorithm. I then split the data into traininga and test sets, set the ending period for the training data with an offset of 3 months, scaled the data, and used the SVC classifier from SKLearn's SVM method to fit the training data and make predictions on the testing data. I then generated a classification report and a prediction dataframe that shows the predicted values, actual returns, and strategy returns. The final step was to create a cumulative return plot that shows the actual returns vs the strategy returns. This plot represents the baseline model results and is shown below:

![baseline](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Baseline.png)



![training size](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Adjusted_Training_Size.png)
![sma](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Adjusted_SMA.png)
![linear regression](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Linear_Regression.png)



---

## Contributors

Tyler Castleberry was the sole contributor to this project. 

---

## License

MIT License

Copyright (c) 2022 Tyler Castleberry

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.