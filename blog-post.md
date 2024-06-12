Predicting User Churn with Sparkify Data

![image](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/1aa3b742-46f8-4349-87fe-81491d999848)


Predicting User Churn with Sparkify Data


**Introduction**

The Sparkify project is a data science initiative aimed at predicting user churn for a music streaming service. In this project, we leverage the power of Apache Spark to handle a substantial dataset and develop a predictive model to identify users who are likely to cancel their subscription. The primary goal is to understand user behavior, define churn, engineer relevant features, and evaluate machine learning models to accurately predict churn.

**Dataset Description**

The dataset used for this project is a subset of the full Sparkify dataset, containing user interactions with the music streaming service. It includes various features such as user demographics, session information, song data, and timestamps of user actions. The dataset is provided in JSON format and is loaded into a Spark DataFrame for analysis.

**Approach**

**Data Loading and Cleaning** 
We begin by loading the dataset into a Spark DataFrame and performing data cleaning to ensure its integrity. This involves identifying and handling missing or invalid data, such as records without user IDs or session IDs.

**Exploratory Data Analysis (EDA)**

Next, we conduct exploratory data analysis to gain insights into user behavior. We examine the distribution of various events, user activity patterns over time, and other key metrics to understand the dataset's characteristics.

#### Distribution of User Genders

![Distribution of User Genders](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/9c03b909-28dc-46a5-b9e6-ef290902f83d)

*Description: This bar plot illustrates the distribution of user genders in the dataset.*

#### User Activity by Hour of the Day

![User Activity by Hour of the Day](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/ffe6f823-8cd1-43ea-8fef-7026a74682a1)

*Description: This line plot shows the number of user activities recorded during each hour of the day.*

### Top 10 Popular Songs

![Top 10 Popular Songs](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/e7757e84-a426-47e0-87f6-8a5746128a91)

*Description: This bar plot displays the top 10 most popular songs based on the number of plays.*

**Defining Churn**

Churn is defined based on the occurrence of the "Cancellation Confirmation" event, indicating users who have decided to cancel their subscription. Additionally, we consider "Downgrade" events as potential indicators of churn.

**Feature Engineering**

We identify and engineer several features that are indicative of user churn. These features include metrics such as the number of songs played, frequency of interactions with different features, session duration, and time since the last session.

**Modeling**

The dataset is split into training, validation, and test sets. We evaluate several machine learning models, including Logistic Regression, Decision Tree Classifier, and Random Forest Classifier, using the F1 score as the primary metric. The model with the highest F1 score on the validation set is selected as the winning model.

#### Comparison of F1 Scores

*Description: This bar plot compares the F1 scores of different models on the validation set.*

**Results**

![F1 score_result](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/80082cea-1226-425f-b5d0-94abdddbfc30)

The Decision Tree Classifier emerged as the best-performing model, achieving the highest F1 score among the evaluated models. This performance can be attributed to its ability to capture complex relationships, interpretability, effective feature selection, and optimized hyperparameters.

**Conclusion**

The Sparkify project demonstrates the effectiveness of using Apache Spark for analyzing large datasets and building predictive models for user churn prediction. By understanding user behavior and leveraging machine learning techniques, companies can proactively identify users at risk of churn and implement strategies to retain them.

**Future Work**

Future work could include further refining the feature engineering process, experimenting with ensemble methods, exploring advanced machine learning techniques, and deploying the predictive model in a real-world environment. Additionally, continuous monitoring and optimization of the model would be essential to maintain its accuracy and relevance over time.

Link to GitHub Repository: https://github.com/anhtran192/Data-Scientist-Capstone
