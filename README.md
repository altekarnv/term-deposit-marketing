# term-deposit-marketings

In this project, we were given the data coming from direct marketing efforts of a European banking institution (Client). The client was interested in developing a robust machine learning system that leverages information coming from the call center data. The marketing campaign involved making a phone call to a client's customer, often multiple times to ensure a product subscription, in this case a term deposit. All customer information that might reveal personal information was removed due to privacy concerns. Ultimately, the client was looking for ways to improve the success rate for calls made to customers for any product that their clients offer. Towards this goal, this project provided a trained machine learning model to predict the success of each marketing call.
Data

    The provided data had a mix of categorical and numerical features.
    The target variable was highly imbalanced since the proportion of the customers that subscribed to a term deposit was significantly less than those who did not. We used random undersampling approach to deal with theimbalanced data.
    Numerical veriables from the data set had outliers. These outliers were treated using IQR approach where outlying values were capped (ceil or floor) to the upper and lower whiskers respectively.

Customer Segmentation

From the EDA, following points were evident about the customers who were most likely to subscribe to a term deposit.

    October and March months showed the highest conversion rate though the calls made during these months were among the least.
    Among first five months by number of customers contacted, June (6.21%) month showed the highest conversion rate followed by November (6.11%).
    Among the customers called on cellular phone, about 9% subscribed to a term deposit followed by 7.1% of the customers contacted over telephone.
    Customers having no loan showed better conversion rate (7.61%) than those having active loans (5.48%).
    Customers not having own housing were more likely to subscribe to a term deposit as compared to those having their own housing.
    Customers who had defaulted on a loan were less likely to subscribe to a term deposit
    Customers who had completed tertiary education were most likely to subscribe to a term deposit followed by the ones who had completed secondary education.
    Single and divorced customers were more likely to suscribe to a term deposit than the married customers.
    Students and retred professional were most likely to subscribe to a term deposit followed by management professionals and unemployed individuals Housemaids, service professionals and blue collared workers were least likely to subscribe to a term deposit
    Customers contacted on 30th of any month were most likely to subscribe to a term deposit.
    Younger customers showed more willingness to subscribe to a term deposit compared to older customers
    There were some customers who subscribed to the term deposit in spite having a negative bank balance. This might be an anomaly in the data.
    Most customers were contacted either once or twice. These customers were more likely to subscribe to a term deposits compared to the ones who were called more often.

Modeling

Several classification models were compared without any hyperparameter tuning. Since the dataset had categorical variables, it was important to select a model that can offer interpretability, speed and accuracy while dealing with categorical variables.

AdaBoost, LightGBM, and Support Vector Machine based classifiers were found to be the best performing models. Among those, LightGBM was selected for further analysis and training given its intepretability, speed, accuracy and ability to deal with categorical variables natively. The model was evaluated using train-test split and 5-fold cross validation approach and found to hit the required accuracy of 81% in every fold as well as test data.
Feature Importance

From the analysis of the trained model, it was clear that the most important features that the client should focus on are the following:

    duration
    day
    balance
    age

The default feature was the least significant feature.
