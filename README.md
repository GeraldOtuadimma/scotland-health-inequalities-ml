# Scotland Healthy Life Expectancy: Statistical and Machine Learning Analysis

This repository contains the Python analysis for the MSc dissertation **Data-Driven Modelling of Health Inequalities in Scotland, UK, Using Statistical Analysis and Machine Learning**.

It includes the data, Jupyter notebook, tables and figures used in the study.

## Study focus

The project examines differences in Healthy Life Expectancy (HLE) across Scottish council areas. It looks at how deprivation, employment, education and other population characteristics are related to HLE at birth and compares different machine learning models for prediction.

## Getting started

Open `notebook/Scotland_HLE_Statistical_ML_Analysis.ipynb` in JupyterLab or VS Code.

To run the analysis:

1. Create a Python environment.
2. Install the packages in `requirements.txt`.
3. Open the notebook.
4. Run the notebook from beginning to end.

The main results are saved in the `results/` folder.

## Project contents

* `notebook/`: Jupyter notebook containing the analysis.
* `data/`: datasets and data dictionary.
* `results/figures/`: figures from the analysis.
* `results/tables/`: statistical and machine learning results.
* `results/ANALYSIS_SUMMARY.md`: summary of the main findings.
* `requirements.txt`: Python packages used.

## Data

The HLE dataset contains 1,280 rows covering 32 Scottish council areas, two sexes and 20 age groups.

The main modelling analysis uses HLE at birth, giving 64 council-sex observations across the 32 councils. The other age groups are used for descriptive analysis and are not treated as separate modelling observations.

The study combines HLE data with council-level deprivation, economic and population characteristics.

## Analysis

The statistical analysis includes descriptive statistics, group comparisons, deprivation analysis, correlation analysis and regression modelling.

Machine learning models are compared for HLE prediction, including Linear Regression, Ridge, Elastic Net, Random Forest, Gradient Boosting, Support Vector Regression and k-Nearest Neighbours.

A secondary classification analysis groups HLE into Low, Middle and High categories.

The models use council-grouped cross-validation to reduce the risk of the same council appearing in both training and test data.

## HLE groups

The 64 council-sex observations are grouped as:

* **Low:** 58.1 years or below
* **Middle:** above 58.1 to 62.0 years
* **High:** above 62.0 years

These groups are based on the study data and are not clinical or official policy thresholds.

## Important notes

* The analysis uses council-level data, not individual-level data.
* The findings show associations and predictions, not causation.
* The main modelling analysis is based on 64 observations, so the machine learning results should be interpreted with caution.
* HLE confidence intervals are used for interpretation and are not model predictors.
* The HLE data are from the 2022-2024 release. Comparisons with earlier releases should consider changes in the statistical method and data series.

## Data sources

The study uses data from:

* National Records of Scotland (NRS) Healthy Life Expectancy statistics.
* Scottish Index of Multiple Deprivation (SIMD) 2020.
* Scotland's Census 2022 and related population and economic data.

The `data/Scotland_HLE_Data_Dictionary.csv` file provides information about the variables, units and sources.

## Software

The analysis was carried out using Python 3.12 with JupyterLab or VS Code.

The packages used are listed in `requirements.txt`.
