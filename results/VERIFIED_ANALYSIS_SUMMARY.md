# Verified analysis summary

## Study scope

The master data contain 1,280 HLE observations across 32 Scottish council areas, two sexes and 20 HLE age groups. HLE at birth is the primary outcome, producing 64 sex-specific observations in 32 paired council clusters. The full age dataset is used descriptively. Predictive evaluation holds out complete councils.

## Descriptive and statistical results

- Female HLE at birth averaged 60.32 years and male HLE averaged 59.90 years.
- The mean female-minus-male HLE difference was 0.42 years (council-bootstrap 95% CI 0.21 to 0.64).
- The HLE gap between councils in the least- and most-exposed deprivation quartiles was 11.59 years (bootstrap 95% CI 9.19 to 14.41).
- In the primary adjusted ecological regression, a one-standard-deviation increase in severe-deprivation exposure was associated with 3.23 fewer HLE years (council-clustered 95% CI 0.85 to 5.61 years lower).

## Continuous HLE prediction

- Random Forest had the lowest out-of-fold regression MAE at 1.85 years (council-bootstrap 95% CI 1.32 to 2.48).
- Its RMSE was 2.61 years and its out-of-fold R-squared was 0.72.
- Ridge and Gradient Boosting produced MAEs of 1.89 and 1.92 years respectively.
- The Dummy mean benchmark had MAE of 4.04 years.

## Low, Middle and High HLE classification

- Low HLE was defined as 58.1 years or below, Middle HLE as above 58.1 and up to 62.0 years, and High HLE as above 62.0 years.
- The resulting classes contained 22 Low, 20 Middle and 22 High observations.
- Random Forest was the strongest direct classifier, with balanced accuracy 0.764 (council-bootstrap 95% CI 0.621 to 0.896), macro-F1 0.766, weighted kappa 0.824 and one-versus-rest macro ROC AUC 0.867.
- The confusion matrix contained no direct Low-to-High or High-to-Low errors.
- Converting the strongest regression predictions into the same bands produced 76.6% accuracy and weighted kappa 0.824.
- The regression-derived and directly classified bands agreed for 62 of 64 observations, or 96.9%.

## Model interpretation and sensitivity

- Severe-deprivation exposure was the dominant feature across the Ridge, Random Forest, permutation and exact reference-based Shapley views.
- Its mean absolute Shapley contribution was 2.19 HLE years, followed by long-term-sick inactivity at 0.78 years and degree-level education at 0.38 years.
- The maximum exact Shapley additivity error was below 1.5 x 10^-14.
- Adding health-context indicators changed Ridge MAE from 1.89 to 1.94 years and Gradient Boosting MAE from 1.92 to 1.88 years.
- Inverse-variance weighting gave a deprivation estimate of 3.09 fewer HLE years per standard deviation (council-clustered 95% CI 1.56 to 4.62 years lower).
- Across 32 leave-one-council-out refits, the adjusted deprivation estimate ranged from 1.94 to 3.80 fewer HLE years per standard deviation and remained negative in every refit.

## Reproducibility record

- 147 notebook cells, including 73 executed code cells.
- No user-defined functions or lambda expressions.
- No execution errors and no code cell with more than one visible output.
- 44 reproducible CSV result tables and 44 high-resolution PNG figures.
- Random seed: 25928399.

The three HLE bands describe relative positions in the 2022-2024 Scottish council-sex distribution. The wider interpretation and limitations are reserved for Chapter 5.
