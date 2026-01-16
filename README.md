# Mobile User Behavior Classification

# Description
this project intends to classify mobile users into behavior categories based on smartphone usage patterns such as app usage time, screen-on duration, data consumption, and battery drain. This project demonstrates exploratory data analysis, feature engineering, and model comparison using Logistic Regression and Random Forest, highlighting clear patterns in the dataset for classification.

# Dataset
The dataset contains information about mobile users, including:

- Numerical features:  
  - App Usage Time (min/day)  
  - Screen On Time (hours/day)  
  - Battery Drain (mAh/day)  
  - Number of Apps Installed  
  - Data Usage (MB/day)  
  - Age  
  - Engineered ratios: Usage_per_App, Data_per_Hour, Drain_per_Hour
  
- Categorical features:
  - Operating System  
  - Gender  
  - Age Group (binned from Age)  
  - Device Model
- Target:
  - User Behavior Class (categorical)

- Rows: 700 

#Exploratory Data Analysis (EDA)
Key insights from EDA:

- Usage-related features (app time, screen-on time, data usage) have monotonic trends across user classes.  
- Age distribution is uneven, but user behavior class is not strongly influenced by the age group.  
- Device model and OS show minor influence.  
- Created ratio-based features to capture efficiency metrics per app and per hour.  

#Visualizations include: 
- Distribution of features by user class  
- Bar plots and stacked charts for categorical relationships  

#Feature Engineering & Preprocessing
- Numerical features were standardized using StandardScaler.  
- Categorical features were encoded with OneHotEncoder (OS, Gender) and OrdinalEncoder (Age Group).  
- Ensured no data leakage between train and test sets.  

#Modeling
Two models were trained and compared:

1. Logistic Regression (multinomial, lbfgs solver)  
   - Used as a baseline due to near-linear separability observed in EDA.

2. Random Forest Classifier (n_estimators=300, max_features='sqrt')  
   - Used to capture non-linear patterns and compare performance.

Pipeline: preprocessing → model  

Results
- Logistic Regression: 100% accuracy, perfect classification due to separable features.  
- Random Forest: 100% accuracy, confirming patterns captured by a non-linear model.  

#conclusion: The exceptional performance is attributed to the well-structured data and strong feature-target relationships, not overfitting or leakage.

Metrics reported:
- Accuracy, Macro F1-score, Confusion Matrix, Classification Report
