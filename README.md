# Income Classification and Segmentation

This repository presents an analysis of U.S. Census data with the goal of predicting whether an individual's annual income exceeds $50,000. The project applies standard data processing, exploratory analysis, classification models, and segmentation strategies.

## Workflow

### Data Preparation
The dataset was cleaned and relevant features were selected. Categorical variables were handled using target encoding, while numerical variables were kept in their original form. To address class imbalance, downsampling of the majority class was applied in the training data.

### Exploratory Data Analysis
Basic descriptive statistics and visualizations were used to understand the distribution of variables, class imbalance, and relationships between demographic characteristics and income.

### Modeling
Three classification models were implemented:
- **Logistic Regression** as a baseline model.  
- **Decision Tree** to illustrate interpretability through decision rules.  
- **XGBoost** as a gradient boosting model providing the strongest predictive performance.  

Models were evaluated on the test set using accuracy, ROC–AUC, confusion matrices, and classification reports.

### Segmentation
Segmentation was carried out in two ways:
1. **Model segmentation**: separate models were trained for male and female subpopulations to evaluate whether performance improves compared to a single overall model.  
2. **Score-based segmentation**: marketing-oriented groups were defined using predicted probabilities and gender, identifying subgroups with a substantially higher likelihood of high income.

### Visualization
The analysis includes ROC curves for each model, confusion matrices for selected classifiers, a tree visualization for the Decision Tree model, and ROC curves by gender segments. Segmentation results are summarized in tables.
