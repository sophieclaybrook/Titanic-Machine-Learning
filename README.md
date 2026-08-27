# Titanic - Machine Learning from Disaster

## Project Overview

This project explores the Kaggle **Titanic - Machine Learning from Disaster** classification problem. The aim is to predict whether a passenger survived based on features such as age, sex, passenger class and fare.

I completed this project to develop practical machine learning experience and apply statistical and mathematical knowledge from my degree to a real-world dataset.

## Dataset

The dataset contains:

- 891 training passengers with known survival outcomes
- 418 test passengers with unknown outcomes
- 11 original features

Key features include:

- `Pclass` - Passenger class
- `Sex` - Passenger sex
- `Age` - Passenger age
- `SibSp` - Number of siblings/spouses aboard
- `Parch` - Number of parents/children aboard
- `Fare` - Ticket fare
- `Embarked` - Port of embarkation

The target variable was `Survived`, where 1 represents survival and 0 represents non-survival.

## Methodology

### Data Cleaning

- Missing `Age` values were replaced using the median age.
- Missing `Embarked` values were replaced using the mode.
- `Cabin` was removed due to the large proportion of missing values.

### Feature Engineering

Two additional features were created:

- **Title** - Extracted from passenger names to capture information relating to age, sex and social status.
- **FamilySize** - Calculated using `SibSp + Parch + 1`.

Categorical variables including `Sex`, `Embarked` and `Title` were encoded into numerical variables.

## Machine Learning Models

Three classification models were compared:

1. Logistic Regression
2. Decision Tree
3. Random Forest

The training data was split into 80% training and 20% validation data.

### Model Results

| Model | Validation Accuracy |
|---|---:|
| Logistic Regression | 79.33% |
| Decision Tree | 76.54% |
| Random Forest | **83.24%** |

The Random Forest achieved the highest validation accuracy among the three untuned models.

## Hyperparameter Tuning

`GridSearchCV` with 5-fold cross-validation was used to tune the Random Forest.

The best combination was:

- `n_estimators = 300`
- `max_depth = 5`
- `min_samples_split = 2`

This achieved a cross-validation accuracy of **83.28%**.

However, the tuned model achieved **81.56%** on the held-out validation set, compared with **83.24%** for the untuned Random Forest. Therefore, the original untuned Random Forest was selected for the Kaggle submission.

## Key Findings

One notable finding was the large difference in survival rates between women and men. **74.20% of women survived compared with 18.89% of men.** Survival was also considerably higher among first-class passengers than third-class passengers.

These patterns are consistent with the historical circumstances surrounding the Titanic evacuation.

## Kaggle Submission

The final untuned Random Forest model was submitted to Kaggle and achieved a submission score of **0.74**.

## Skills Demonstrated

- Python
- Pandas
- NumPy
- Data cleaning
- Exploratory data analysis
- Feature engineering
- Data preprocessing
- Categorical encoding
- Logistic Regression
- Decision Trees
- Random Forest
- Hyperparameter tuning
- GridSearchCV
- Cross-validation
- Model evaluation
- GitHub

## Future Improvements

Potential extensions to this project include:

- Developing additional features
- Testing additional machine learning models
- Exploring ensemble methods
- Further improving model performance

## References

Breiman, L. (2001). *Random Forests*. Machine Learning, 45, 5-32.
