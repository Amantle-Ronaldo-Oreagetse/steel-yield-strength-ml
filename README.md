# Machine Learning Prediction of Steel Yield Strength

## Overview

This project investigates whether machine learning can predict the yield strength of steels using chemical composition and processing information.

The dataset contains 3,234 steel records with chemical composition, processing-condition information, dimensional information, and measured yield strength.

## Research Question

Can machine-learning models predict the yield strength of steels from chemical composition and processing information?

## Objective

To investigate whether incorporating processing information alongside chemical composition improves machine-learning prediction of steel yield strength.

## Dataset Source and Attribution

### Dataset

This project uses the **Steel Database with Labelled Clusters**, obtained from Mendeley Data. The dataset is part of the publication *A Database of Mechanical Properties of Steels* by Birbilis, Ghorbani, and Zhao (2025).

The database contains 3,234 steel entries, including chemical compositions, processing conditions, mechanical properties, and processing-condition classifications grouped into 12 labelled clusters. These data provide the basis for exploring machine-learning approaches to predicting steel properties.

The target variable is yield strength, measured in MPa.

### Accessing the Dataset

The original dataset is publicly available on Mendeley Data:

* **Dataset title:** A Database of Mechanical Properties of Steels
* **Repository:** Mendeley Data
* **Direct link:** https://data.mendeley.com/datasets/jmwb9ddd43/1
* **DOI:** https://doi.org/10.17632/jmwb9ddd43.1
* **File used:** `Steel database with labelled clusters.xlsx`
* **Licence:** Creative Commons Attribution 4.0 International (CC BY 4.0)

To access the data:

1. Visit the [Mendeley Data dataset page](https://data.mendeley.com/datasets/jmwb9ddd43/1).
2. Locate the file named `Steel database with labelled clusters.xlsx`.
3. Download the file using the available download option.
4. Place the downloaded file in the appropriate directory of your project and follow the data-loading instructions in the project notebooks or scripts.


### Attribution and Usage

The original dataset was created by Nick Birbilis, Marzie Ghorbani, and Shujing Zhao. It is used in this project for educational and research purposes to investigate machine-learning methods for steel property analysis and prediction.

The original dataset is attributed to its authors. Any data cleaning, preprocessing, feature selection, model development, evaluation, and visualisations performed in this project are part of the project's own analytical workflow.

Users wishing to reuse or redistribute the dataset should consult the original Mendeley Data record and comply with its CC BY 4.0 licence, including appropriate attribution.


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