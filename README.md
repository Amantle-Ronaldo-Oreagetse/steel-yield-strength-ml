# Machine Learning Prediction of Steel Yield Strength

## Overview

This project investigates whether machine learning can predict the yield strength of steels using chemical composition and processing information.

The dataset contains 3,234 steel records with chemical composition, processing-condition information, dimensional information, and measured yield strength.

## Research Question

Can machine-learning models predict the yield strength of steels from chemical composition and processing information?

## Objective

To investigate whether incorporating processing information alongside chemical composition improves machine-learning prediction of steel yield strength.

## Dataset

The dataset contains 3,234 steel records.

Features include:

- Chemical composition
- Processing condition
- Cluster information
- Tempering temperature
- Quench temperature
- Quench-stage information
- Reheat stages
- Case depth
- Round size

The target variable is yield strength, measured in MPa.

The original dataset is not included in this repository. Users must obtain the data from an authorised source before reproducing the analysis.

## Methodology

The analysis followed a progressive modelling approach:


1. Dataset inspection and exploratory data analysis.
2. Preparation of chemical composition and processing-related features.
3. Development of a composition-only baseline model.
4. Development and evaluation of a Random Forest regression model.
5. Five-fold cross-validation.
6. Feature-importance analysis.
7. Out-of-fold prediction and error analysis.
8. Evaluation of model limitations and potential future improvements.

## Final Model

The final model was a Random Forest using chemical composition, cluster information, and structured processing/dimensional features.

Five-fold cross-validation produced:

- R²: 0.939 
- MAE: 36.65 MPa

## Key Findings

Including processing information substantially improved predictive performance compared with using chemical composition alone.

The most important predictive features included:

- Quench-stage type
- Fe content
- Cluster number
- Round size
- First tempering temperature

Feature importance represents predictive contribution within this dataset and should not be interpreted as evidence of causation.

Error analysis showed that performance varied across steel clusters and was weaker for the high-strength subset.

These results describe performance within the available dataset and do not establish performance on independent external data.

## Limitations

- Some processing variables contain substantial missing information.
- Direct microstructural measurements are not included in the model.
- Prediction errors are larger for the high-strength subset.
- Independent external validation has not yet been performed.

## Tools

- Python
- pandas
- NumPy
- Matplotlib
- scikit-learn
- Jupyter Notebook


## Future Work

Future work could include:

- Improve the completeness of processing information.
- Increase the number of high-strength steel observations.
- Compare alternative machine-learning models.
- Evaluate the final model on an independent dataset.


## Reproducibility

The analysis is documented in `steel_yield_strength.ipynb`.

Install the required Python packages listed in `requirements.txt` before running the notebook.