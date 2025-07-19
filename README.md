# :🏏 IPL Score Prediction Using Machine Learning
This project aims to predict the final score of an IPL (Indian Premier League) first innings based on various match features like batting team, bowling team, overs, runs, wickets, and performance in the last 5 overs.

📁 Dataset
Dataset: ipl.csv

Shape: (76014, 15)

Columns include match details, batting/bowling teams, current score, overs, player info, and final total.

📊 Exploratory Data Analysis (EDA)
Initial steps involved:

Viewing data types and column names

Previewing the dataset with .head()

Exploring unique teams and distributions

🧹 Data Cleaning
Steps performed:

Removed unwanted columns: Dropped irrelevant fields like mid, venue, batsman, etc.

Filtered consistent teams: Retained only 8 IPL teams that were consistent across seasons.

Removed first 5 overs: Eliminated rows with overs < 5.0.

Converted date: Changed the date column from string to datetime.

📈 Feature Engineering
One-Hot Encoding: Categorical columns bat_team and bowl_team encoded using pd.get_dummies().

Rearranged columns: To keep features and target aligned.

Train-Test Split:

Train: Seasons 1–9 (2008–2016)

Test: Season 10 (2017)

Removed date column after splitting.

🔥 Feature Correlation Heatmap
Plotted using seaborn to identify strongly correlated features.

🤖 Model Building
Models Tested:
Linear Regression

Decision Tree Regressor

Random Forest Regressor

AdaBoost Regressor (Boosted Linear Regression)

Model Evaluation Metrics:
MAE: Mean Absolute Error

MSE: Mean Squared Error

RMSE: Root Mean Squared Error

Model	MAE	MSE	RMSE
Linear Regression	12.12	251.00	15.84
Decision Tree	17.09	531.05	23.04
Random Forest	13.76	330.21	18.17
AdaBoost (Linear)	12.21	249.60	15.79

✅ Final Model Chosen: Linear Regression (best trade-off between simplicity and accuracy)

🧠 Prediction Function
Custom prediction function predict_score() takes match state parameters like:

Batting team

Bowling team

Overs

Runs

Wickets

Last 5 overs’ performance

