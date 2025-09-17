# Income Classification and Segmentation

This repository contains code and analysis for predicting whether an individual's annual income exceeds $50,000 using U.S. Census data. The project applies several machine learning models and explores segmentation strategies for both modeling and marketing perspectives.

## Project Structure
- **Module A**: Feature preparation  
- **Module B**: Train/Test split by calendar year  
- **Module C**: Target encoding of categorical variables  
- **Module D**: Feature/target separation  
- **Module E**: Downsampling for class balance  
- **Modeling**: Logistic Regression, Decision Tree, XGBoost  
- **Segmentation**:  
  - Model segmentation (train/evaluate separate models by gender)  
  - Score-based segmentation (rules using predicted probability and gender)  

## Methods
- Categorical variables are encoded using target encoding on the training set.  
- Train/Test split follows the dataset’s year variable (1994 as train, 1995 as test).  
- Logistic Regression, Decision Tree, and XGBoost are applied for classification.  
- Segmentation is performed in two ways:  
  1. Separate models by gender to compare performance.  
  2. Define target groups using prediction scores combined with demographic rules.  

## Results
- Logistic Regression provides a baseline for interpretability.  
- Decision Tree illustrates key splits and variable importance.  
- XGBoost achieves the strongest performance among the tested models.  
- Segmentation helps identify subgroups with higher likelihood of high income.  

## Visualizations
- ROC curves for Logistic Regression, Decision Tree, and XGBoost.  
- Confusion matrices for selected models.  
- Decision tree visualization (limited depth).  
- ROC comparison by gender segmentation.  
- Score-based segmentation summary tables.  
