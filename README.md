# Machine Learning Assignment 2
## Classification Models and Performance Evaluation

**Course:** M.Tech Artificial Intelligence and Machine Learning  
**Dataset:** Adult Income Classification Dataset

---

## 1. Problem Statement

The objective of this assignment is to implement and evaluate five machine learning classification algorithms using a real-world dataset.

The experiment includes data exploration, preprocessing, model training, performance evaluation, visualization and comparison of classification algorithms.

The target variable is income, which is classified into two categories:
- Income <=50K
- Income >50K

## 2. Dataset Description

**Dataset:** Adult Income Classification Dataset

**Source:** UCI Machine Learning Repository

https://archive.ics.uci.edu/dataset/2/adult

The Adult Income dataset contains demographic and employment-related information used to predict whether an individual's annual income exceeds $50,000.

### Dataset characteristics

- Original records: 48,842
- Features: 14
- Target variable: income
- Classification type: Binary classification
- Records after duplicate removal: 48,790

### Reason for dataset selection

The dataset was selected because it contains both numerical and categorical features, has sufficient observations for classification experiments and represents a binary classification problem. It also provides an opportunity to examine missing values and class imbalance.

### Target variable

| Target | Encoding |
|---|---:|
| Income <=50K | 0 |
| Income >50K | 1 |

### Class distribution

| Income category | Percentage |
|---|---:|
| Income <=50K | 76.07% |
| Income >50K | 23.93% |

The dataset has an imbalanced class distribution, making precision, recall, F1 score and MCC important evaluation metrics.

## 3. Data Preprocessing

The following preprocessing steps were implemented:

1. Identified missing values in categorical features.
2. Identified and removed 52 duplicate records.
3. Separated independent features and target variable.
4. Encoded the target variable into binary values.
5. Applied an 80:20 train-test split.
6. Used stratified sampling to maintain class distribution.
7. Used random state 42 for reproducibility.
8. Applied median imputation and StandardScaler to numerical features.
9. Applied most-frequent imputation and OneHotEncoder to categorical features.
10. Fitted preprocessing transformations only on training data.

The processed training dataset contained 105 features after one-hot encoding.

## 4. Machine Learning Models

Five classification algorithms were implemented using the same dataset:

1. Logistic Regression
2. Decision Tree Classifier
3. K-Nearest Neighbors
4. Gaussian Naive Bayes
5. Random Forest Classifier

### Model configurations

| Model | Configuration |
|---|---|
| Logistic Regression | max_iter=1000 |
| Decision Tree | random_state=42 |
| KNN | n_neighbors=5 |
| Gaussian Naive Bayes | Default configuration |
| Random Forest | n_estimators=100, random_state=42 |

## 5. Evaluation Metrics

The following six metrics were used:

- Accuracy
- Area Under the ROC Curve (AUC)
- Precision
- Recall
- F1 Score
- Matthews Correlation Coefficient (MCC)

### Model Performance Comparison

| ML Model | Accuracy | AUC | Precision | Recall | F1 Score | MCC |
|---|---:|---:|---:|---:|---:|---:|
| Logistic Regression | 0.8477 | 0.9020 | 0.7258 | 0.5848 | 0.6477 | 0.5572 |
| Decision Tree | 0.8082 | 0.7430 | 0.5957 | 0.6182 | 0.6067 | 0.4801 |
| KNN | 0.8315 | 0.8558 | 0.6624 | 0.6040 | 0.6319 | 0.5239 |
| Gaussian Naive Bayes | 0.6173 | 0.8329 | 0.3777 | 0.9242 | 0.5363 | 0.3855 |
| Random Forest | 0.8519 | 0.8995 | 0.7164 | 0.6314 | 0.6712 | 0.5781 |

## 6. Model Performance Observations

### Logistic Regression
- Achieved the highest AUC score of 0.9020.
- Achieved the highest precision of 0.7258.
- Demonstrated strong discrimination between income categories.
- Recall was comparatively lower at 0.5848.

### Decision Tree
- Achieved an accuracy of 80.82%.
- Obtained the lowest AUC score of 0.7430.
- Demonstrated moderate classification performance.
- Its overall performance was lower than Random Forest and Logistic Regression.

### K-Nearest Neighbors
- Achieved an accuracy of 83.15%.
- Obtained an AUC score of 0.8558.
- Demonstrated balanced performance across precision and recall.
- Performed better than the Decision Tree in overall evaluation.

### Gaussian Naive Bayes
- Achieved the highest recall of 0.9242.
- Obtained comparatively low precision of 0.3777.
- Identified most of the positive income cases but also produced a relatively high number of false positives.
- Achieved the lowest accuracy among the five models.

### Random Forest
- Achieved the highest accuracy of 85.19%.
- Obtained the highest F1 score of 0.6712.
- Achieved the highest MCC score of 0.5781.
- Demonstrated the strongest overall performance among the five classification models.

## 7. Overall Winner

Based on the evaluation results, Random Forest was identified as the strongest overall classification model for this dataset.

It achieved the highest accuracy, F1 score and Matthews Correlation Coefficient.

However, Logistic Regression performed best in terms of AUC and precision, while Gaussian Naive Bayes achieved the highest recall.

This demonstrates that the selection of a classification model depends on the evaluation metric and the specific requirements of the classification problem.

## 8. Visualizations

The notebook includes the following visualizations:

1. Income class distribution.
2. Comparison of all six evaluation metrics.
3. Confusion matrix comparison of all five classification models.
4. ROC curve comparison of all five models.

These visualizations provide a graphical understanding of the performance and classification behaviour of each model.

## 9. Repository Contents

The repository contains the following project files:

- Assignment_2.ipynb – Complete implementation and analysis.
- README.md – Project description, preprocessing, model configurations and results.
- requirements.txt – Python dependencies.
- test_data.csv – Test dataset used for model evaluation.
- models/ – Saved trained classification models.
- model_predictions.csv – Predictions generated by all five models.
- model_probabilities.csv – Predicted class probabilities.
- model_evaluation_metrics.csv – Final model performance comparison.

## 10. Execution Instructions

1. Clone or download the GitHub repository.
2. Install the required Python dependencies.
3. Open Assignment_2.ipynb using Jupyter Notebook.
4. Execute the notebook cells sequentially.
5. Review the preprocessing, model training and evaluation results.
6. Review the generated visualizations and exported files.

Install dependencies using:

```bash
pip install -r requirements.txt
```

## 11. Conclusion

The experiment successfully implemented five machine learning classification algorithms on the Adult Income Classification dataset.

All models were evaluated using six performance metrics.

Random Forest demonstrated the strongest overall performance, while Logistic Regression achieved the highest AUC and precision. Gaussian Naive Bayes achieved the highest recall.

The experiment highlights the importance of evaluating classification algorithms using multiple performance metrics rather than relying on accuracy alone.
