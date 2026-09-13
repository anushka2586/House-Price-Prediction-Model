# 🏠 House Price Prediction using Machine Learning

A machine learning project that predicts residential house prices using the Ames Housing dataset. The project covers exploratory data analysis, data cleaning, missing-value handling, outlier treatment, categorical encoding, model training, evaluation, and final price prediction.

## 📌 Project Overview

The goal of this project is to build a regression model capable of predicting house prices based on features such as:

* Overall house quality
* Living area
* Garage capacity
* Basement area
* Number of bathrooms
* Year built and remodeled
* Neighborhood
* Other property characteristics

The project explores multiple regression algorithms and compares their performance using standard evaluation metrics.

## 📊 Dataset

The project uses the **Ames Housing dataset** from the Kaggle House Prices competition.

* Training samples: 1,460
* Test samples: 1,459
* Original training features: 80
* Target variable: `SalePrice`

The training dataset contains both numerical and categorical features describing different characteristics of each house.

## 🔍 Exploratory Data Analysis

The analysis includes:

* Dataset structure and statistical summaries
* Missing-value analysis
* Correlation analysis
* Distribution of house prices
* Relationship between important features and `SalePrice`
* Neighborhood-wise price comparison
* Correlation heatmaps

Some of the features showing strong relationships with `SalePrice` include:

* `OverallQual`
* `GrLivArea`
* `GarageCars`
* `GarageArea`
* `TotalBsmtSF`
* `1stFlrSF`
* `FullBath`

## 🧹 Data Preprocessing

The preprocessing workflow includes:

* Removing columns with excessive missing values
* Handling categorical missing values using meaningful `"None"` categories where appropriate
* Filling numerical missing values using suitable reference values
* Handling missing `LotFrontage` values using neighborhood-based median values
* Removing the `Id` column before modeling
* Handling remaining missing values
* Detecting and removing two extreme `GrLivArea` outliers
* One-hot encoding categorical features

## 📈 Model Development

Multiple regression models were trained and evaluated:

1. Linear Regression
2. Log-Transformed Linear Regression
3. Random Forest Regression
4. Ridge Regression
5. Lasso Regression

A logarithmic transformation was also applied to the `SalePrice` target to reduce skewness and improve regression performance.

## 🏆 Model Comparison

| Model                             |            MAE |           RMSE |   R² Score |
| --------------------------------- | -------------: | -------------: | ---------: |
| Linear Regression                 |     $17,428.77 |     $23,998.89 |     0.8957 |
| Log-Transformed Linear Regression |     $14,666.76 |     $20,750.18 |     0.9221 |
| Random Forest                     |     $16,346.32 |     $23,906.78 |     0.8965 |
| Ridge Regression                  |     $14,505.01 |     $19,923.49 |     0.9281 |
| **Lasso Regression**              | **$14,064.20** | **$19,341.65** | **0.9323** |

### Final Model

The **Lasso Regression model with a log-transformed target variable** achieved the best validation performance among the models tested.

* **MAE:** $14,064.20
* **RMSE:** $19,341.65
* **R² Score:** 0.9323

The results show that regularization and target transformation improved the performance of the regression models compared with the initial baseline.

## 🏅 Kaggle Submission

The final model was also used to generate predictions for the Kaggle House Prices competition.

**Kaggle score:** `0.13650` RMSE

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Jupyter Notebook

## 📁 Project Structure

```text
House-Price-Prediction-Model/
│
├── housepriceprediction.ipynb
├── train.csv
├── test.csv
├── submission.csv
├── .gitignore
└── README.md
```

## 💡 Key Takeaways

This project helped explore the complete workflow of a regression-based machine learning problem:

**Data → EDA → Cleaning → Preprocessing → Feature Encoding → Model Training → Evaluation → Model Comparison → Prediction**

One of the key findings was that the more complex Random Forest model did not outperform the regularized linear models on the validation set. This highlighted the importance of evaluating models based on actual performance rather than assuming that a more complex algorithm will always perform better.

## 🚀 Future Improvements

Possible improvements for a future version include:

* Cross-validation for more robust model evaluation
* Additional feature engineering
* Hyperparameter tuning
* Gradient boosting models
* A reusable preprocessing and modeling pipeline
* Deployment as an interactive house-price prediction application

## 👩‍💻 Author

**Anushka Saini**

B.Tech CSE (Data Science) Student

Interested in Data Analytics, Machine Learning, and Data Science.
