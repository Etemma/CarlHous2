
# California Housing Price Prediction
## Project Overview

This project uses machine learning regression techniques to predict median house values in California based on housing, demographic and geographical features.
The objective was to explore the dataset, establish a baseline model, train different regression algorithms and identify the model with the best predictive performance.
Dataset

- Source: Scikit-learn California Housing Dataset
- Observations: 20,640
- Features: 8
- Target variable: "MedHouseVal"
- Missing values: None
- Duplicate records: None

The target variable represents median house values in units of $100,000.

## Tools and Libraries

- Python
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
- Jupyter Notebook

## Methodology

1. Data Exploration

- Examined dataset dimensions, data types and descriptive statistics.
- Checked for missing values and duplicate records.
- Investigated feature relationships and target distribution.
- Examined geographical patterns and potential outliers.

2. Data Preparation

- Separated independent variables (X) from the target variable (y).
- Split the dataset into training (80%) and testing (20%) sets.
- Used a random state of 42 for reproducibility.

3. Model Development

Four regression models were evaluated:

1. DummyRegressor – established a baseline using the mean target value.
2. Linear Regression – modelled linear relationships between features and house values.
3. Random Forest Regressor – captured more complex, non-linear relationships.
4. Tuned Random Forest Regressor – restricted tree complexity using hyperparameter adjustments.

4. Model Evaluation

Models were evaluated using:

- Mean Absolute Error (MAE)
- Root Mean Squared Error (RMSE)
- R-squared (R²)

## Results

Model| MAE| RMSE| R²
DummyRegressor| 0.924| 1.168| -0.00029
Linear Regression| 0.536| 0.737| 0.6009
Random Forest| 0.730| 1.040| 0.196
Tuned Random Forest| 0.330| 0.510| 0.8046

The tuned Random Forest achieved the best test performance.

Overfitting Analysis

The original Random Forest achieved a training R² of approximately 0.973 but performed considerably worse on the test data.

After tuning, the training R² was 0.9077 while the test R² was 0.8046.

This indicates improved generalisation and a reduction in overfitting.

## Feature Importance

Median income ("MedInc") was the most influential feature, with an importance score of approximately 0.563.

Average occupancy ("AveOccup") followed with approximately 0.136.

These results indicate that median income contributed substantially more to the model's predictions than the other individual features.

Feature importance indicates predictive contribution, not causation.

## Key Findings

- Median income was the strongest predictor of median house values.
- Linear Regression outperformed the initial Random Forest model.
- The initial Random Forest showed substantial overfitting.
- Hyperparameter tuning improved Random Forest test performance.
- The tuned Random Forest achieved an R² of approximately 0.8046.

## Limitations

- The target variable is capped at 5.0 ($500,000), limiting the model's ability to distinguish higher-value properties.
- Random train-test splitting does not establish how well the model generalises to future housing markets.
- Feature importance does not establish causal relationships.
- Further validation and hyperparameter optimisation could improve confidence in the model.

## Conclusion

The tuned Random Forest Regressor was the best-performing model, explaining approximately 80.46% of the variation in median house values on the test dataset.

The project demonstrated the importance of establishing a baseline, comparing algorithms, evaluating overfitting and tuning model parameters.
