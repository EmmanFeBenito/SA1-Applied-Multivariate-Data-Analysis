# Multivariate Analysis of the Physicochemical Characteristics of Portuguese Vinho Verde Wines

## Research Questions
1. **MANOVA:** Do red and white wines differ significantly in their overall physicochemical characteristics when several characteristics are considered simultaneously?
2. **PCA:** Can the 11 physicochemical measurements of wine be summarized using a smaller number of principal components while retaining a substantial proportion of the total variability?
3. **EFA:** What underlying latent dimensions or factors explain the relationships among the physicochemical characteristics of wine?

## Dataset Description
This study utilizes a combined dataset of 6,497 Portuguese "Vinho Verde" wine samples, comprising 1,599 red wines and 4,898 white wines. The data includes 11 continuous physicochemical variables (such as fixed acidity, chlorides, and residual sugar), wine color, and a sensory quality score. Prior to analysis, 1,177 duplicate observations were removed, resulting in a final analytical dataset of 5,320 observations.

## Dataset Source
The dataset is publicly available from the **UCI Machine Learning Repository** and is licensed under a Creative Commons Attribution 4.0 International (CC BY 4.0) license. 
*   **Original Study:** Cortez, P., Cerdeira, A., Almeida, F., Matos, T., & Reis, J. (2009). Modeling wine preferences by data mining from physicochemical properties. *Decision Support Systems*, 47(4), 547-553.
*   **Source URL:** [Wine Quality Dataset](https://archive.ics.uci.edu/dataset/186/wine+quality)

## Statistical Methods
The analysis was conducted using Python and integrates three primary multivariate techniques:
*   **Exploratory Data Analysis (EDA):** Descriptive statistics, distribution histograms, comparative boxplots, and correlation matrices.
*   **Multivariate Analysis of Variance (MANOVA):** Pillai's Trace statistic was utilized due to assumption violations (heteroscedasticity and multivariate non-normality) to test simultaneous group differences, supported by follow-up univariate ANOVAs.
*   **Principal Component Analysis (PCA):** Dimensionality reduction utilizing Z-score standardized variables, scree plots, and the Kaiser (eigenvalue > 1) criterion.
*   **Exploratory Factor Analysis (EFA):** Principal Axis Factoring with a Promax (oblique) rotation to identify latent variable structures and account for natural chemical correlations.

## Summary of Major Findings
*   **Color Distinction:** Red and white wines exhibit profound, statistically significant differences in their baseline chemical profiles (specifically regarding volatile acidity, chlorides, fixed acidity, and sulphates). Wine color drives approximately 63.1% of the overall variance across these traits.
*   **Dimensionality Reduction:** Both PCA and EFA successfully reduced the 11 physicochemical variables into three robust dimensions. 
*   **Latent Chemical Structure:** The chemical makeup of these wines is heavily governed by three latent dynamics: Preservation Techniques (sulfur levels), Fermentation Body (density, residual sugar, and alcohol), and Core Sourness (acidity and pH). 
*   **Model Limitations:** The Kaiser-Meyer-Olkin (KMO) Measure of 0.4013 indicates poor overall factorability for the full 11-variable set, suggesting some unique variables fragment the latent structure when forced into a single EFA model.

## Software Used
*   **Language:** Python
*   **Environment:** Google Colab
*   **Libraries:** `pandas`, `numpy`, `matplotlib`, `seaborn`, `scipy`, `statsmodels`, `scikit-learn`, `factor_analyzer`

## Instructions for Reproducing the Analysis
1. Clone this repository to your local machine.
2. Ensure the following directory structure is intact, with the original datasets located in the `data/` folder:
   ```text
   SA1-Applied-Multivariate-Data-Analysis/
   ├── data/
   │   ├── winequality-red.csv
   │   └── winequality-white.csv
   ├── code/
   │   └── SA1_Wine_Analysis.ipynb
   ├── output/
   │   ├── figures/
   │   └── tables/
   └── report/
       └── SA1_Wine_Quality_Report.pdf
