Employee Attrition Risk Prediction (Logistic Regression)

Problem Statement

Employee attrition is costly and disruptive.
The goal of this project is to identify employees at risk of leaving so that preventive actions can be taken early.

This is framed as a binary classification problem on tabular HR data.

⸻

Dataset
• Source: IBM Employee Attrition dataset
• Rows: 1,470
• Columns: 35
• Target variable: Attrition
• 1 → Employee leaves
• 0 → Employee stays

The dataset is imbalanced, with significantly fewer attrition cases.

⸻

Approach

1. Data Preparation
   • Separated features (X) and target (y)
   • Converted target labels from categorical to numeric
   • Applied one-hot encoding to categorical features using pd.get_dummies

2. Train / Test Split
   • 80% training, 20% testing
   • Stratified split to preserve class distribution

3. Model
   • Logistic Regression
   • Two configurations evaluated:
   • Default Logistic Regression
   • Logistic Regression with class_weight='balanced'

⸻

Evaluation Strategy

Because attrition cases are the minority class, recall for Attrition = Yes was chosen as the primary metric.

Accuracy alone was not considered sufficient due to class imbalance.

⸻

Results

Baseline Logistic Regression
• Recall (Attrition = Yes): 0.23
• The model missed 77% of employees who actually left
• Not suitable for attrition risk detection

Logistic Regression with Class Weighting
• Recall (Attrition = Yes): 0.64
• The model correctly identified 64% of employees who left
• Significant improvement with a single targeted adjustment

⸻

Conclusion

Applying class weighting substantially improved the model’s ability to detect employee attrition.
This demonstrates how simple, well-targeted changes can outperform more complex approaches when dealing with imbalanced data.

⸻

Technologies Used
• Python
• Pandas
• NumPy
• Scikit-learn

⸻

Key Takeaways
• Imbalanced datasets require metric-driven evaluation
• Accuracy can be misleading in classification problems
• Logistic Regression remains a strong baseline when used correctly
• Small, disciplined changes often outperform “fancy” techniques
