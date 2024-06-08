Predicting User Churn with Sparkify Data

![image](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/1aa3b742-46f8-4349-87fe-81491d999848)

**Project Overview**

The Sparkify project is a comprehensive data science endeavor aimed at predicting user churn for a music streaming service. In this project, we leverage Spark to handle a substantial dataset and build a predictive model to identify users who are likely to cancel their subscription. The primary goal is to understand user behavior, define churn, engineer relevant features, and evaluate machine learning models to predict churn accurately.

**Problem Statement**

User churn is a critical issue for subscription-based businesses. Identifying users who are likely to churn allows companies to take proactive measures to retain them. This project aims to build a model that predicts whether a user will churn based on their interaction with the service.

**Metrics**

Given the imbalanced nature of churned versus non-churned users, we use the F1 score as our primary metric. The F1 score is a harmonic mean of precision and recall, providing a balance between false positives and false negatives.

**Data Exploration and Cleaning**

Load and Clean Dataset: We start with a mini-dataset (mini_sparkify_event_data.json) and perform data cleaning to ensure its integrity. This involves:
Removing records with missing user IDs or session IDs.
Handling null values and correcting data types.

Exploratory Data Analysis: We conduct an exploratory data analysis (EDA) to gain insights into user behavior. Key observations include:

Distribution of events such as song plays, likes, and skips.
User activity patterns over time.

**Defining Churn**

Churn is defined based on the "Cancellation Confirmation" event. Users who trigger this event are labeled as churned. As an additional task, we consider "Downgrade" events to understand potential indicators of churn.

Data Exploration Post-Churn Definition: After labeling churn, we further explore the dataset to compare behaviors between churned and non-churned users:

Average number of songs played per session.
Interaction with different features like liking a song or adding to a playlist.

Feature Engineering: We identify and engineer several features that are indicative of user churn. These features include:

Number of songs played.
Frequency of different events (e.g., thumbs up, thumbs down, add to playlist).
Session duration and number of sessions.
Time since last session.

**Modeling**

Data Splitting

The data is split into training, validation, and test sets to ensure robust model evaluation.

Model Evaluation

We evaluate several machine learning models, including Logistic Regression, Decision Tree Classifier, and Random Forest Classifier. The performance is measured using the F1 score:

Logistic Regression: F1 Score = 0.767

Decision Tree Classifier: F1 Score = 0.791

Random Forest Classifier: F1 Score = 0.778

Best Model: Decision Tree Classifier

The Decision Tree Classifier outperforms other models due to its ability to capture complex relationships, interpretability, and effective feature selection. Key reasons for its superior performance include:

Model Complexity: Captures intricate patterns in the data.
Interpretability: Provides clear decision paths.
Feature Selection: Naturally selects the most informative features at each split.
Hyperparameter Tuning: Optimized through tuning parameters like tree depth.
Results
The Decision Tree Classifier achieves the highest F1 score of 0.791, making it the most effective model for predicting churn in this dataset. The model's interpretability and ability to capture complex relationships contribute significantly to its performance.

**Conclusion**

Reflection: This project provided valuable insights into user behavior and the factors contributing to churn. One of the main challenges was handling the imbalanced dataset and ensuring that the model generalizes well.

Improvement - Future work could include:

Incorporating more advanced feature engineering.
Exploring additional machine learning models such as Gradient Boosting Machines or Neural Networks.
Using a larger dataset to improve model robustness.

Link to GitHub Repository: https://github.com/anhtran192/Data-Scientist-Capstone
