**Predicting User Churn with Sparkify Data**

![image](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/1aa3b742-46f8-4349-87fe-81491d999848)




**Introduction**

The Sparkify project is a data science initiative aimed at predicting user churn for a music streaming service. In this project, we leverage the power of Apache Spark to handle a substantial dataset and develop a predictive model to identify users who are likely to cancel their subscription. The primary goal is to understand user behavior, define churn, engineer relevant features, and evaluate machine learning models to accurately predict churn.

**Description of Input Data**

The dataset for this project is a subset (128MB) of the full dataset (12GB) from Sparkify's user activity logs. It includes user interactions with the music streaming service, captured in JSON format. Key attributes in the dataset are:

  userId: Unique identifier for each user
  
  sessionId: Unique identifier for each session
  
  page: The type of user interaction (e.g., NextSong, Thumbs Up, Logout)
  
  song: The song name
  
  artist: The artist name
  
  ts: Timestamp of the event
  
  length: Length of the song played
  
  level: User subscription level (free or paid)
  
  gender: User's gender
  
  location: User's location

These attributes are essential for understanding user behavior and building predictive models for churn.

**Strategy for Solving the Problem**

The approach involves the following steps:

Data Loading and Cleaning: Load the dataset, identify and handle missing or invalid data. 

Exploratory Data Analysis (EDA): Conduct EDA to gain insights into the data and identify patterns related to user churn.

Feature Engineering: Create new features that capture user behavior and interactions with the service.

Modeling: Train various machine learning models to predict churn.

Evaluation: Evaluate model performance using appropriate metrics and select the best model.

We employ Spark's powerful data processing capabilities to handle the large dataset efficiently and use machine learning libraries to build and evaluate models.

**Discussion of the Expected Solution**

The proposed solution involves using Spark to preprocess the data, engineer features, and train machine learning models. The workflow integrates:

Data Preprocessing: Cleaning and transforming raw data into a structured format suitable for modeling. 

Feature Engineering: Creating meaningful features from raw data to capture user behavior.

Model Training: Using machine learning algorithms such as Logistic Regression, Decision Trees, and Random Forests to predict churn.

Model Evaluation: Assessing models using metrics like F1 score to ensure robustness and reliability.

Each component is designed to work seamlessly within the Spark framework, leveraging its distributed computing capabilities.

**Metrics with Justification**

The primary metric for evaluating model performance is the F1 score. This metric is chosen because it balances precision and recall, making it suitable for imbalanced datasets like churn prediction. Precision measures the proportion of true positive predictions, while recall measures the proportion of actual positives identified. The F1 score provides a single metric that accounts for both, offering a comprehensive assessment of model performance.

**Exploratory Data Analysis (EDA)**

During EDA, we explore the distribution of user activities, analyze user demographics, and identify patterns associated with churn. Key findings include:

User Activity: Patterns in song plays, session lengths, and interaction types. 

Demographics: Distribution of user gender and location.

Churn Indicators: High correlation between certain activities (e.g., "Cancellation Confirmation") and churn.

Visualizations such as histograms, bar plots, and heatmaps help uncover these insights and guide feature engineering.

Example of some visualizazions: 

#### Distribution of User Genders

![Distribution of User Genders](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/9c03b909-28dc-46a5-b9e6-ef290902f83d)

*Description: This bar plot illustrates the distribution of user genders in the dataset.*

#### User Activity by Hour of the Day

![User Activity by Hour of the Day](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/ffe6f823-8cd1-43ea-8fef-7026a74682a1)

*Description: This line plot shows the number of user activities recorded during each hour of the day.*

### Top 10 Popular Songs

![Top 10 Popular Songs](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/e7757e84-a426-47e0-87f6-8a5746128a91)

*Description: This bar plot displays the top 10 most popular songs based on the number of plays.*

**Data Preprocessing**

Data preprocessing involves:

Handling Missing Values: Dropping records with missing userId or sessionId. 

Data Transformation: Converting timestamps to human-readable formats and creating new features (e.g., hour of the day).

Cleaning: Removing invalid entries and ensuring data consistency.

This step ensures the dataset is clean, structured, and ready for feature engineering and modeling.

**Modeling**

We employ several machine learning algorithms:

Logistic Regression: A linear model for binary classification.

Decision Tree Classifier: A non-linear model that splits data based on feature values.

Random Forest Classifier: An ensemble method that combines multiple decision trees for better performance.

Each model is trained on the preprocessed dataset and evaluated using the F1 score.

**Hyperparameter Tuning**

Hyperparameter tuning is performed using grid search and random search techniques. Key hyperparameters include:

Learning Rate: For gradient-based models like Logistic Regression. 

Tree Depth: For Decision Tree and Random Forest models.

Number of Trees: For Random Forest.

Tuning these hyperparameters optimizes model performance on the validation set.

**Results**

The evaluation results indicate that the Decision Tree Classifier outperforms other models with an F1 score of 0.79. The model captures complex relationships in the data and provides interpretable insights into churn prediction. Key performance metrics include precision, recall, and F1 score, with detailed visualizations for each model.

#### Comparison of F1 Scores

![F1 score_result](https://github.com/anhtran192/Data-Scientist-Capstone/assets/147739264/80082cea-1226-425f-b5d0-94abdddbfc30)

**Explanation of Model Performance**

Logistic Regression: This model assumes a linear relationship between the features and the target variable. While it provides a baseline, it may not capture the non-linear patterns in user behavior effectively, leading to lower performance compared to more complex models.

Decision Tree Classifier: This model can capture non-linear relationships by splitting the data based on feature values. It inherently performs feature selection, which helps in identifying the most informative features. The ability to handle non-linearity and perform feature selection contributes to its superior performance.

Random Forest Classifier: This ensemble method improves robustness by combining multiple decision trees. However, in this case, the Random Forest did not significantly outperform the single Decision Tree, possibly due to the complexity and overfitting of the trees. Hyperparameter tuning was critical, but the Decision Tree's simplicity proved advantageous.

**Evaluation of the Final Model**

The final model, the Decision Tree Classifier, was evaluated in detail. Key qualities and parameters included:

Tree Depth: Optimal depth was determined through hyperparameter tuning. A deeper tree captures more complexity but risks overfitting.

Splitting Criteria: Gini impurity was used to measure the quality of splits, ensuring balanced and informative partitions.

Feature Importance: The model inherently ranks features by their importance, providing insights into which user behaviors are most indicative of churn.

**Conclusion**

The Decision Tree Classifier is the best-performing model for predicting user churn in the Sparkify dataset. It effectively captures user behavior patterns and provides actionable insights. The project demonstrates the power of combining Spark with machine learning to handle large-scale data and build robust predictive models.

**Reflection**

Key Findings and Insights

Feature Engineering: Developing meaningful features was crucial for model performance. Features like session length and song count were significant indicators of user engagement and churn.

Model Performance: The Decision Tree Classifier performed best, likely due to its ability to capture complex relationships in the data and its inherent feature selection capability.

Interesting Aspects and Challenges

Handling Imbalanced Data: Managing the imbalance between churned and non-churned users was challenging. Using the F1 score helped balance precision and recall, providing a more accurate assessment of model performance.

Hyperparameter Tuning: Finding the optimal hyperparameters for each model required extensive experimentation. This process was critical for enhancing model performance but was time-consuming and computationally intensive.

Summary: The project successfully demonstrated a comprehensive approach to predicting user churn using machine learning with Apache Spark. The insights gained can help Sparkify implement strategies to retain users, thereby improving customer satisfaction and business outcomes. Future improvements could involve enriching features, exploring ensemble models, and optimizing for real-time predictions.

**Future Work**

Future improvements could include:

Feature Enrichment: Incorporating additional features such as user engagement metrics and social interactions. 

Model Ensembles: Combining multiple models to improve prediction accuracy.

Scalability: Optimizing the pipeline for scalability and real-time predictions.

These enhancements can further improve the model's performance and applicability.

Link to GitHub Repository: https://github.com/anhtran192/Data-Scientist-Capstone
