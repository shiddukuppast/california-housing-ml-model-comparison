# California Housing Price Prediction

A machine learning project focused on predicting California house prices and comparing different regression approaches on a tabular dataset.

The project evaluates traditional machine learning models and a neural network, followed by hyperparameter tuning of XGBoost to improve predictive performance.

## 📌 Overview

The objective of this project is to predict the `median_house_value` of California housing districts using demographic, housing, and geographical features.

Instead of using a single model, multiple approaches were implemented and evaluated to understand how different algorithms perform on a tabular regression problem.

The models explored in this project are:

- Linear Regression
- Decision Tree Regressor
- Random Forest Regressor
- XGBoost Regressor
- Artificial Neural Network (ANN)

After the initial model comparison, XGBoost was selected for further hyperparameter tuning because it provided the strongest performance among the models tested.

## Dataset

The project uses the California Housing dataset.

The target variable is:

`median_house_value`

The dataset contains information such as:

- Longitude
- Latitude
- Housing median age
- Total rooms
- Total bedrooms
- Population
- Households
- Median income
- Ocean proximity

## Machine Learning Workflow

The project follows an end-to-end machine learning workflow:

```text
Dataset
   ↓
Exploratory Data Analysis
   ↓
Data Cleaning
   ↓
Feature Engineering
   ↓
Categorical Encoding
   ↓
Train / Validation / Test Split
   ↓
Feature Scaling
   ↓
Model Training
   ↓
Model Evaluation
   ↓
Model Comparison
   ↓
XGBoost Hyperparameter Tuning
   ↓
Final Evaluation


Exploratory Data Analysis

Initial analysis was performed to understand:

Feature distributions
Missing values
Relationships between features
Target variable distribution
Numerical and categorical features

Histograms and other visualizations were used during the exploratory analysis.

Feature Engineering

Additional features were created from the existing variables to provide more useful information to the models.

Rooms per House
rooms_per_house = total_rooms / households
Bedrooms Ratio
bedrooms_ratio = total_bedrooms / total_rooms
People per House
people_per_house = population / households

These features provide normalized information about the composition and characteristics of each housing district.


Data Preprocessing

The following preprocessing techniques were used:

Missing-value imputation
One-hot encoding of categorical variables
Standardization of numerical features
Train/validation/test splitting

The scaler was fitted only on the training data and then applied to the validation and test sets to avoid data leakage.

🧠 Models    

Linear Regression

Linear Regression was used as a baseline model to establish a reference performance for the regression task.

Decision Tree

A Decision Tree Regressor was trained to capture nonlinear relationships between the input features and house prices.

Random Forest

Random Forest was used as an ensemble tree-based model to improve generalization compared with a single decision tree.

XGBoost

XGBoost was trained as a gradient boosting regression model.

It provided the strongest performance among the initial models and was therefore selected for further optimization.

Artificial Neural Network

A feed-forward Artificial Neural Network was implemented using TensorFlow/Keras.

The ANN consisted of multiple fully connected layers using ReLU activation functions and a single linear output neuron for regression.

Early stopping was used during training to monitor validation loss and restore the best model weights.



📈 Model Evaluation
The models were evaluated using the following regression metrics:

RMSE
Root Mean Squared Error measures the average magnitude of prediction errors while giving greater weight to larger errors.

MAE
Mean Absolute Error represents the average absolute difference between actual and predicted values.

MSE
Mean Squared Error calculates the average squared prediction error.

R² Score
R² measures how much of the variance in the target variable is explained by the model.


📊 Results

Model Comparison 
Initial results from the experiments:

Model	                      RMSE          MAE           MSE            R²
Linear Regression	         69121.10	  49657.39	 4777727123.05	  0.635401
Decision Tree	             70394.16     43321.31   4955338719.46    0.621847
Random Forest	             49808.01     31927.01   2480838807.81    0.810682
XGBoost	                     43769.23	  28329.03	 1915746234.88	  0.853805
Artificial Neural Network	 64181.09     45093.04	 4119212540.45	  0.685654


XGBoost Hyperparameter Tuning

Since XGBoost produced the best initial results, hyperparameter tuning was performed to search for a better configuration.

Parameters explored during tuning included:

n_estimators
max_depth
learning_rate
subsample
colsample_bytree
min_child_weight
gamma

The purpose of tuning was to find a better balance between model complexity, learning rate, and generalization.

The tuned model was then evaluated using the same regression metrics used during the initial model comparison.

Neural Network vs XGBoost

One of the goals of this project was to compare a neural network with a traditional machine learning approach on tabular data.

The initial results showed:

Metric               XGBoost	                  ANN
RMSE	            43769.23                    64181.09
MAE	                28329.03                    45093.04
MSE	                1915746234.88               4119212540.45
R²	                0.853805                    0.685654

Based on these experiments, XGBoost performed significantly better than the ANN on this particular dataset.

This does not imply that XGBoost is always better than neural networks for every tabular dataset. The result is specific to the dataset, preprocessing, features, and model configurations used in this project.
```text


🚀 Key Learning Outcomes
This project helped explore several important machine learning concepts:

Exploratory data analysis
Feature engineering
Handling missing values
Categorical feature encoding
Feature scaling
Avoiding data leakage
Train/validation/test splitting
Regression evaluation metrics
Comparing different machine learning algorithms
Building neural networks for regression
Early stopping
XGBoost
Hyperparameter tuning
Model selection based on experimental results

A key takeaway from the project was that a more complex model does not necessarily provide better results. Model performance depends heavily on the characteristics of the data and the suitability of the algorithm for the problem.

🛠️ Technologies Used
Python
Pandas
NumPy
Matplotlib
Seaborn
Scikit-learn
XGBoost
TensorFlow
Keras
Jupyter Notebook


Conclusion

This project demonstrates an end-to-end approach to solving a tabular regression problem.

Multiple regression algorithms were trained and evaluated, followed by a comparison between traditional machine learning and a neural network.

XGBoost achieved substantially better initial performance than the ANN on this dataset and was therefore selected for hyperparameter tuning.

The project emphasizes the importance of experimentation, proper preprocessing, model comparison, and evidence-based model selection rather than assuming that a particular algorithm will always perform best.

👨‍💻 Author
Siddesh S Kuppast