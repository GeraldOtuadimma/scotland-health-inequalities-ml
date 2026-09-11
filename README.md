# Scotland Healthy Life Expectancy: Complete Statistical and Machine-Learning Analysis

This is the reproducible empirical package for the dissertation **Data-Driven Modelling of Health Inequalities in Scotland, UK, Using Statistical Analysis and Machine Learning**. It supports the methodology, results and discussion chapters and is designed to remain auditable for publication.

## Start here

Open `notebook/Scotland_HLE_Complete_Statistical_ML_Analysis.ipynb` in JupyterLab or the VS Code Jupyter extension. The notebook is already executed, so every table and figure can be reviewed before rerunning it.

To reproduce the analysis:

1. Create a Python environment.
2. Install the packages in `requirements.txt`.
3. Open the notebook from this project folder.
4. Select **Run All**.

The raw CSV is never overwritten. Re-running the notebook recreates every analysis table and publication figure using Python.

## Package contents

- `notebook/`: the complete executed Jupyter notebook.
- `data/`: the analysis dataset and publication data dictionary.
- `results/figures/`: 44 high-resolution PNG figures.
- `results/tables/`: 44 machine-readable statistical and ML result tables.
- `results/VERIFIED_ANALYSIS_SUMMARY.md`: concise results and interpretation boundaries.
- `requirements.txt`: minimal reproducibility dependencies.

## Analytical design

- Master data: 1,280 HLE rows, 32 councils, two sexes and 20 HLE age groups.
- Primary outcome: HLE at birth (`age_group = <1`), giving 64 sex-specific observations in 32 paired council clusters.
- All-age rows: used for descriptive age patterns, not treated as 1,280 independent units.
- Statistics: descriptive summaries, paired tests, deprivation gaps, council-bootstrap intervals, council-level FDR-controlled Spearman correlations, PCA, VIF, staged ecological regression, council-clustered standard errors and residual diagnostics.
- Regression ML: Dummy, Linear Regression, Ridge, Elastic Net, Random Forest, Gradient Boosting, Support Vector Regression and k-Nearest Neighbours.
- Classification ML: a secondary Low, Middle and High HLE task using Dummy, Multinomial Logistic, Random Forest, Gradient Boosting, Support Vector Machine and k-Nearest Neighbours.
- Validation: nested cross-validation grouped by council; preprocessing and tuning occur inside training folds.
- Regression-classification consistency: the strongest regression model's predictions are converted to the same three HLE bands and compared with direct classification.
- Interpretation: regression coefficients, Random Forest importance, permutation importance, partial dependence and exact reference-based Shapley values with an additivity check.
- Sensitivity: core upstream predictors are compared with an extended set containing outcome-adjacent health context. The feature-set comparison uses nested council-grouped tuning. Inverse-variance weighting and leave-one-council-out refitting test the stability of the adjusted deprivation association.

## Important safeguards

- No related rows from the same council enter both training and test data.
- HLE confidence limits are interpretation fields, never predictors.
- Council codes and names are identifiers, not model features.
- Urban/rural classification is not included because a verified council-area crosswalk was not available for the supplied data.
- No synthetic observations, fabricated joins or manual outcome edits are used.
- Low, Middle and High HLE are sample-derived tertile bands, not clinical or policy thresholds.
- Three-class results include predicted probabilities, balanced and macro metrics, weighted kappa, extreme-error checks and a class-feature overlap audit.
- Results are ecological, cross-sectional associations and predictions. They do not establish causation or individual risk.
- HLE 2022-2024 is Official Statistics in Development. Direct comparison with pre-2025 APS-only releases is inappropriate; use the revised NRS new-method back series for trend analysis.

## Software

Use Python 3.12 with JupyterLab or VS Code. The complete statistical, machine-learning and visual analysis is implemented in Python. CSV is used for the source data because it is transparent, portable and easy to reproduce. Excel is needed only if you choose to inspect the exported result tables. The reference-based Shapley analysis is calculated transparently in the notebook and does not require the external `shap` package.
