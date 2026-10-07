# RiskLens

## Corporate Credit Rating Prediction with Machine Learning

RiskLens is a machine learning project that explores whether corporate financial characteristics can be used to predict credit rating categories.

The project compares multiple classification models and evaluates their ability to distinguish between 10 credit rating levels using financial indicators such as return on equity, liquidity, company size, and cost-to-income ratios.

## Project Objective

The goal of this project was to answer:

> Can corporate financial characteristics be used to accurately predict credit rating categories?

To explore this question, I trained and compared three classification models:

- Logistic Regression
- Random Forest
- Gradient Boosting

## Dataset

The dataset contains:

- 5,000 observations
- 10 credit rating categories
- 6 financial predictor variables
- Even class distribution across rating categories

The credit rating classes include:

- very_bad
- bad
- poor
- below_average
- average
- above_average
- good
- very_good
- excellent
- outstanding

The financial features used in the models were:

- `commeqta`
- `llploans`
- `costtoincome`
- `roe`
- `liqassta`
- `size`

The identifier variable `spid` was excluded from modeling because it does not represent a financial characteristic.

## Project Workflow

The project followed this general process:

1. Loaded and inspected the dataset
2. Checked data types, missing values, and class distribution
3. Removed the identifier column
4. Performed exploratory data analysis
5. Split the data into training and testing sets
6. Built a Logistic Regression baseline
7. Built a Random Forest model
8. Built a Gradient Boosting model
9. Compared model performance
10. Analyzed feature importance
11. Examined model errors using a confusion matrix

## Exploratory Data Analysis

Before modeling, I examined the distribution of the financial variables and how they differed across credit rating categories.

Several variables showed meaningful differences between rating classes, suggesting that the dataset contained useful predictive information.

However, many neighboring rating categories also showed overlapping feature distributions, indicating that the classification problem would likely require nonlinear models.

## Model Performance

| Model | Accuracy | Macro F1 |
|---|---:|---:|
| Logistic Regression | 58.1% | 0.577 |
| Random Forest | 79.0% | 0.790 |
| Gradient Boosting | **80.7%** | **0.807** |

Gradient Boosting achieved the strongest overall performance.

The nonlinear ensemble models substantially outperformed the Logistic Regression baseline, suggesting that the relationships between financial characteristics and credit ratings are not purely linear.

## Logistic Regression

Logistic Regression was used as the baseline model.

The model achieved:

- Accuracy: 58.1%
- Macro F1 Score: 0.577

Performance was strongest for more distinct credit rating categories, while several middle rating categories were more difficult to distinguish.

## Random Forest

Random Forest significantly improved performance compared with the baseline.

The model achieved:

- Accuracy: 79.0%
- Macro F1 Score: 0.790

This improvement suggested that nonlinear relationships and interactions between financial features were important for predicting credit ratings.

## Gradient Boosting

Gradient Boosting produced the strongest results.

The model achieved:

- Accuracy: 80.7%
- Macro F1 Score: 0.807

This model was selected as the best-performing model based on overall accuracy and macro F1 score.

## Feature Importance

Feature importance analysis was used to examine which financial indicators contributed most strongly to the Gradient Boosting model's predictions.

This helped improve interpretability by showing which variables had the greatest influence on model decisions.

## Confusion Matrix

A confusion matrix was used to analyze where the model made classification errors.

The results showed that some rating categories were easier to classify than others, while neighboring credit rating classes were more likely to be confused.

This is especially relevant because credit ratings are naturally ordered, meaning that some classification errors are less severe than others.

## Key Takeaways

- Financial indicators contain meaningful predictive information for credit rating classification.
- Nonlinear models substantially outperformed the linear baseline.
- Gradient Boosting achieved the highest performance.
- Some middle rating categories were more difficult to distinguish.
- Model evaluation should consider more than accuracy alone, especially in multiclass classification problems.

## Technologies Used

- Python
- pandas
- NumPy
- scikit-learn
- matplotlib
- SciPy
- Google Colab

## Limitations

This project has several limitations.

The dataset contains a relatively small set of financial indicators and does not include broader economic conditions, industry-specific variables, or time-based information.

The rating classes are also ordinal, but the current models treat them as independent categories.

## Future Improvements

Future versions of the project could include:

- Hyperparameter tuning
- Cross-validation
- Additional financial indicators
- Ordinal classification techniques
- SHAP-based model interpretability
- XGBoost or LightGBM
- Economic and industry-level variables
- More advanced feature engineering
