# Taxi-Fare-Prediction

# Data Description

The data consists of the following features:

trip_duration: (in seconds)
distance_traveled: (in Km)
num_of_passengers
fare: base fare
tip
miscellaneous_fees
total_fare: The grand total for the ride (this is your prediction target!
surge_applied: Was there a surge pricing applied? Yes or no?

# Data Preprocessing

Removed outliers and invalid values such as negative or zero fares, distances, or durations.
Imputed missing values with KNN Imputer depending on the feature.
Created new features such as speed from existing features.
Scaled numerical features with standardization.

# Model Training

Several machine learning models were trained and evaluated on the data using cross-validation and hold-out validation. The models used were:

XGBoostRF
Random Forest
Linear Regression
Decision Tree
Artificial Neural Network
The metrics used to measure the performance of the models were R2 score and Root Mean Squared Log Error (RMSLE). The results are summarized in the table below:

| Model | R2 Score(Train) | R2 Score(Test) | RMSLE(Test) |
|----------|----------|----------|----------|
| Linear Regression | 0.86894 | 0.88777 | 0.13034 |
| Decision Tree | 0.89272 | 0.90993 | 0.09535 |
| Random Forest | 0.90657 | 0.92208 | 0.08666 |
| XGBoost | 0.88650 | 0.90838 | 0.08704 |
| Artificial Neural Network | - | 0.92344 | 0.09049 |

The best performing model was Random Forest.

# Model Tuning

Hyperparameter tuning was performed on every models using GridSearchCV to find the optimal parameters that would improve the model performance. The tuned models achieved slightly better results than the default models.

# Model Ensembling

An ensemble averaging model was created by combining the predictions of XGBoost and Random Forest models with equal weights. The ensemble model achieved a slightly better result than any individual model, as shown in the table below:

| Model | R2 Score(Train) | R2 Score(Test) | RMSLE(Test) |
|----------|----------|----------|----------|
| Ensemble model | - | 0.92881 | 0.09049 |

# Conclusion

The project demonstrated the use of different machine learning algorithms and data preprocessing techniques to predict the total fare for a taxi ride. The best performing model was ensemble model, followed by Random Forest. The project also showed the importance of feature engineering, feature selection, and hyperparameter tuning to improve the model performance.



