# Income Prediction and Customer Segmentation for Retail Marketing

This project uses U.S. Census data to build a machine learning model that predicts whether an individual's income is above or below $50,000. Based on this model, it develops an actionable customer segmentation strategy to help a retail client improve its targeted marketing efforts.

## 1. Project Objective

The project was designed to address two primary business needs for a retail client:

1.  **Classification**: Develop and validate a robust classifier to predict if an individual's income is greater than or less than $50k, using a rich set of demographic and employment variables.
2.  **Segmentation**: Create a customer segmentation model to identify distinct groups of people for targeted marketing campaigns, and demonstrate how these groups differ and can be strategically approached.

## 2. Dataset

The data for this project is from the 1994 and 1995 Current Population Surveys conducted by the U.S. Census Bureau.

* **Source**: U.S. Census Bureau
* **Content**: Each record contains 40 demographic and employment-related variables, plus an income label (<=$50k or >$50k).
* **Files**:
    * `census-bureau.data`: The main dataset, comma-delimited.
    * `census-bureau.columns`: A file containing the header names for the columns in the data file.

## 3. Methodology

My process followed a structured approach from data exploration to final recommendation.

#### 3.1 Data Preparation & Feature Engineering

This was a critical phase to prepare the data for modeling:
* **Data Cleaning**: Handled missing values and inconsistent placeholders (e.g., `?`) by replacing them with a consistent `'Unknown_Category'` label.
* **Time-Based Split**: The data was split by year: 1994 data was used for training and 1995 data was used for testing. This simulates a real-world scenario of predicting future outcomes based on past data.
* **Target Encoding**: Instead of one-hot encoding, I used target encoding to convert key categorical variables into numerical features. Each category was replaced by the mean income outcome (>50k rate) calculated from the training set. This is a powerful way to capture predictive value in a single feature.
* **Downsampling**: The training data showed a significant class imbalance (many more low-income records). I used downsampling to create a balanced training set, which prevents the model from being biased towards the majority class.

#### 3.2 Modeling

I trained and compared three different models to find the best balance of performance and interpretability:
1.  **Logistic Regression**: Served as a strong, interpretable baseline (Test AUC: 0.92).
2.  **XGBoost**: A powerful gradient boosting model that achieved the highest predictive accuracy (Test AUC: 0.95).
3.  **Decision Tree**: A simple, transparent model, which I constrained to a max depth of 4 to ensure it was easy to understand (Test AUC: 0.92).

**Model Selection:**
While XGBoost had the best performance, it operates as a "black box." For a business context where understanding the "why" is crucial, this is a major drawback. I therefore selected the **Decision Tree** as the final recommended model. It provides competitive performance while being fully transparent, offering clear rules that can directly inform marketing strategy.

#### 3.3 Segmentation Strategy

The final, recommended strategy was not to build separate models for different groups, but to use a **score-based segmentation** approach:
1.  Use the most powerful model (XGBoost) to assign a probability score (0 to 1) to every individual.
2.  Set a high-score threshold (0.80) to identify a small group of high-propensity targets.
3.  Divide this high-score group by gender to create two primary marketing segments: `'High Score Male'` and `'High Score Female'`.

This strategy proved extremely effective, concentrating the high-income individuals into small, actionable groups. The `'High Score Male'` segment showed a **7.6x lift** (7.6 times more likely to be high-income than average), and the `'High Score Female'` segment showed a **5.3x lift**.

## 4. Repository Structure
