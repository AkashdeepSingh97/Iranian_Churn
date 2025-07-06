# Iranian_Churn
# Objective
          The goal of this project is to predict customer churn in an Iranian telecom dataset using machine learning models. By identifying customers likely to churn (leave the service), businesses can implement retention strategies. The dataset contains 3150 customer records with 14 features (all int64), including Call Failure, Complains, Customer Value, and Churn (target: 0 for non-churn, 1 for churn).
# Dataset
        Source:- UCI Machine Learning
        Features:- 13 Predicted and 1 Target
        Characteristics: All columns are int64. Categorical features (Age Group, Tariff Plan, Status, Complains) were one-hot encoded. No missing values.
# Methods
      Preprocessing:
               Encoding: One-hot encoded categorical features (Age Group, Tariff Plan, Status, Complains) to handle their int64 representation.
               Scaling: Applied MinMaxScaler to normalize numerical features.
               Class Imbalance: Used SMOTE to balance the Churn classes (originally imbalanced) by generating synthetic samples.
               Splitting: Split data into 80% training and 20% testing sets with random_state=42
     Modeling:
            Trained three models: Logistic Regression, Random Forest, and XGBoost.
            Random Forest used max_depth=20, min_samples_split=2 n_estimators=100 for interpretability.
            XGBoost used eval_metric='logloss'.
            Evaluated models using Accuracy, Precision, Recall, F1 Score, and ROC AUC.
    Visualizations:
            Random Forest Tree: Visualized one tree from the Random Forest to show decision logic (e.g., Complains drives churn predictions).
            Confusion Matrices: Created for Random Forest and XGBoost to analyze true positives (TP), true negatives (TN), false positives (FP), and false      negatives (FN).
            Performance Chart: Bar chart comparing model metrics with values displayed.
# Results
       Model Performance(Test_set):
           Model                   Accuracy     Precision      Recall      F1-Score      ROC-AUC
           Logistic Regression    0.880414      0.863063       0.903774    0.882949      0.880458
           Random Forest          0.976460      0.970205       0.983019    0.976570      0.976472
           XGBoost                0.981168      0.975746       0.986792    0.981238      0.9811178  
      Key Insights:
          Random Forest was chosen as the best model due to its high F1 Score (0.977) and interpretability (via tree visualization).
          XGBoost slightly outperformed Random Forest (F1 Score: 0.981), but Random Forest was preferred for its balance of performance and explainability.
          Confusion matrices show low false negatives for both models, ensuring most churners are identified (critical for retention).
          Features like Complains and Customer Value were key predictors, as seen in Random Forest tree splits.
# Visualizations
      Random Forest Tree (images/Decision_Tree_Random_Forest.png): Shows decision logic (e.g., high Complains predicts churn).
      Confusion Matrices:
              Random Forest (images/rf_confusion_matrix.png): High TP, low FN.
              XGBoost (images/xgb_confusion_matrix.png): Slightly higher TP, lower FN.
     Performance Chart (images/model_performance_with_values.png): Compares metrics with values on bars.
