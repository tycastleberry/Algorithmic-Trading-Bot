## Algorithmic Trading Bot

The purpose of this project is to create an algorithmic trading bot that learns and adapts to new data and evolving markets. The goal is to implement an algorithmic trading strategy that uses machine learning to automate the trade decisions, adjust the input parameters to optimize the trading algorithm, and train a new model to compare its performance to the baseline model. This project will be coded in Python using a Jupyter notebook. We will use multiple libraries and dependencies, including pandas, matplotlib, and sklearn. 

---

## Baseline Model

The first step is to establish a baseline performance for the trading algorithm. After creating the dataframe, I used short and long window Simple Moving Average (SMA) values to generate trading signals. The short window was set to 4 days, and the long window was set to 100 days. I used these two windows to generate their respective SMA values, then added a column to the dataframe that determines whether the bot should buy long on a stock or sell short. I added another column to generate the returns for the algorithm. I then split the data into traininga and test sets, set the ending period for the training data with an offset of 3 months, scaled the data, and used the SVC classifier from SKLearn's SVM method to fit the training data and make predictions on the testing data. I then generated a classification report and a prediction dataframe that shows the predicted values, actual returns, and strategy returns. The final step was to create a cumulative return plot that shows the actual returns vs the strategy returns. This plot represents the baseline model results and is shown below:

![baseline](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Baseline.png)

This baseline model performed well. From mid to late 2018, the model performed similarly to the actual market. Then towards the end of 2018, the model began outperforming the market and continued to do so through the rest of the available dates.  

---

## Tuned Model #1: Adjusting the Size of the Training Dataset

The next step was to adjust the model's input features to find the parameters that result in the best trading outcomes. My first adjustment was to increase the training period by increasing the DateOffset value from 3 to 6 months. The results of this tuned model are shown below:

![training size](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Adjusted_Training_Size.png)

This tuned model underperformed compared to the actual returns form late 2018 until early 2020. However, in 2020 the strategy overcame this deficit and began outperforming the actual market. It began trending upwards at a rapid rate into 2021.

---

## Tuned Model #2: Adjusting the SMA Input Features

The next adjustment was done by changing the long and short windows for the SMA values. Originally, the short window was set at 4 days, and the long window was set to 100 days. I increased both of these windows. The short window was adjusted to 7 days, and the long window was adjusted to 180 days. The results of these changes to the model are shown in the plot below:

![sma](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Adjusted_SMA.png)

This adjusted model performed below the actual market by a large margin and never recovered. 

---

## Adjusted Models Conclusion

As evidenced above, tuning the size of the training dataset parameters proved to be the more effective strategy for the algorithm. 

---

## Evaluate a New Machine Learning Classifier

The final step of this project was to apply the original model parameters to a new model that utilizes a new classifier. I chose to use the LogisticRegression classifier for my second model. After using this classifier to fit another model, I backtested the model and generated a new classification report. I then plotted the model's returns versus the actual returns, which are shown below:

![linear regression](https://raw.githubusercontent.com/tycastleberry/Challenge14/main/Linear_Regression.png)

This LogisticRegression model greatly underperformed compared to the market from 2018 through 2019. In early 2020, The model began to perform similarly to the market, but never broke through to outperform it.

---

## Evaluation Report

In conclusion, the baseline model ultimately proved to be the best performing model. Among the two tuned models, the adjusted training dataset input parameters provided a better model than the adjusted SMA values. However, the baseline model was still a much better algorithm than either one of these tuned models.

The LogisticRegression model did not perform well when compared to the baseline model or the tuned model with the adjusted training dataset size. The baseline model was profitable for most of the timeframe, but the LogisticRegression model was not and struggled to keep up with the actual market even in the later years of the timeframe. The adjusted training size model was not profitable at first, but eventually overcame this and became profitable. The LogisticRegression model failed to ever become profitable and therefore was the least favorable model. 

The baseline model was the most profitable and appears to offer the least amount of risk. This model would be acceptable to users who are risk-averse because the likelihood of profitability is high without much added risk. The tuned model would be a decent choice for someone who had a large appetite for risk because it was not profitable for a large stretch of time before it eventually got over the hump and beat the market. This model comes with a much higher chance of loss and should be used with caution. The LogisticRegression model should not be used at all. It severely underperformed the other models and the actual market, leaving no reason to use it when compared to the other models.

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
