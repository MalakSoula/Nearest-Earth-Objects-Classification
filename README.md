# Nearest-Earth-Objects-Classification

## Project Overview
This project aims to classify Near-Earth Objects (NEOs) as hazardous or non-hazardous based on their features. The dataset contains information about NEOs from 1910 to 2024, including their orbital parameters and hazard status. The goal is to build a machine learning model to predict whether an NEO is hazardous.

## Dataset
The dataset used in this project is `nearest-earth-objects(1910-2024).csv`. It contains the following features:
- `neo_id`: Unique identifier for the NEO.
- `name`: Name of the NEO.
- `est_diameter_min`: Minimum estimated diameter of the NEO.
- `est_diameter_max`: Maximum estimated diameter of the NEO.
- `relative_velocity`: Relative velocity of the NEO.
- `miss_distance`: Distance by which the NEO missed Earth.
- `orbiting_body`: The body the NEO is orbiting.
- `is_hazardous`: Binary target variable indicating whether the NEO is hazardous (1) or not (0).

## Approach
1. **Data Cleaning**: Removed missing values, duplicates, and irrelevant columns (`neo_id`, `name`, `orbiting_body`).
2. **Exploratory Data Analysis (EDA)**: Analyzed the distribution of the target variable and feature correlations.
3. **Feature Selection**: Used `SelectKBest` with the chi-squared test to select the top 4 features.
4. **Handling Class Imbalance**: Applied SMOTE to balance the dataset.
5. **Model Training**: Trained a Random Forest classifier on the balanced dataset.
6. **Model Evaluation**: Evaluated the model using metrics like accuracy, precision, recall, F1 score, balanced accuracy, and MCC. Visualized the confusion matrix and ROC curve.

## Key Findings
- The dataset was highly imbalanced, with only a small percentage of NEOs being hazardous.
- The top 4 features selected by `SelectKBest` were:
- 1- est_diameter_max
- 2- est_diameter_min
- 3- relative_velocity
- 4- miss_distance.
- After applying SMOTE, the dataset was balanced, and the model performance is:
- 1- Accuracy: [Insert Accuracy]
- 2- Precision: [Insert Precision]
- 3- Recall: [Insert Recall]
- 4- F1 Score: [Insert F1 Score]
- 5- Balanced Accuracy: [Insert Balanced Accuracy]
- 6- MCC: [Insert MCC]
- 7- ROC AUC: [Insert AUC]

# Visualizations
1. Confusion Matrix:

The confusion matrix provides a detailed breakdown of the model's predictions:

1- True Positives (TP): Correctly predicted hazardous NEOs.

2- True Negatives (TN): Correctly predicted non-hazardous NEOs.

3- False Positives (FP): Non-hazardous NEOs incorrectly predicted as hazardous.

4- False Negatives (FN): Hazardous NEOs incorrectly predicted as non-hazardous.

![download (2)](https://github.com/user-attachments/assets/fd33000d-f985-46e1-931c-c7edc18514bc)


3. ROC Curve:

The ROC curve visualizes the trade-off between the True Positive Rate (TPR) and False Positive Rate (FPR) at different classification thresholds. The Area Under the Curve (AUC) is a measure of the model's ability to distinguish between the two classes.

![download (3)](https://github.com/user-attachments/assets/16590678-330c-40ea-b3fe-7cde8ff3cbbe)

   
5. Target Variable Distribution
  
**Before SMOTE**:

The target variable (is_hazardous) was highly imbalanced, with a majority of NEOs classified as non-hazardous. This was visualized using a count plot and a pie chart.

![download](https://github.com/user-attachments/assets/e90df52a-83ac-49e6-9229-5fb2db9e3b18)


**After SMOTE**:

After applying SMOTE, the dataset was balanced, with an equal number of hazardous and non-hazardous NEOs. This was visualized using a count plot.

![download (1)](https://github.com/user-attachments/assets/a22a3824-352d-4d4a-b2cd-91d097a51ade)



## Repository Structure
project/

├── README.md

├── nearest_earth_objects_classification.ipynb

├── nearest-earth-objects(1910-2024).csv

├── images/

│   ├── confusion_matrix.png

│   ├── roc_curve.png

│   ├── before_smote.png

│   └── after_smote.png

└── requirements.txt
