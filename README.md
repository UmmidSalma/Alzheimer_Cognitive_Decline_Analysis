# Exploratory Analysis of Factors Influencing Cognitive Decline

## Classification of Diverse Health Domains Across Regional and Demographic Populations

**Authors:** Ummid Salma Mulla, Pratibha M Patil, P. G. Sunitha Hiremath, Neha Tarannum Pendari  
**Institution:** KLE Technological University, Hubballi, India  
**Dataset:** CDC BRFSS – Alzheimer's Disease and Healthy Aging Data (2015–2022)  
**Data Source:** https://data.cdc.gov/Healthy-Aging/Alzheimer-s-Disease-and-Healthy-Aging-Data/hfr9-rurv/data_preview

### Description

This Jupyter notebook contains an exploratory analysis of factors influencing cognitive decline, focusing on classification of diverse health domains across regional and demographic populations. The analysis includes data loading, preprocessing, exploratory data analysis (EDA) with visualizations, and machine learning models for classification.

### Key Sections

1. **Imports & Configuration**: Loading necessary libraries and setting up the environment.
2. **Load Dataset**: Loading the CDC BRFSS dataset or generating synthetic data if not available.
3. **Data Preprocessing**: Handling missing values, encoding categorical variables, and preparing the target label.
4. **Exploratory Data Analysis (EDA)**: Various plots and analyses including year-wise distribution, health domains segmentation, geographic distribution, trends, and feature importance.
5. **Classification Models**: Three models - correlation-based feature selection, manual feature selection, and Random Forest with SMOTE.
6. **Model Comparison**: Comparing the performance of the models.
7. **Regional Heatmaps**: Heatmap of cognitive decline by year and location.
8. **Conclusion**: Summary of key findings and recommendations.

### Key Findings

- Sharp spike in cognitive decline records in 2019, linked to improved reporting and awareness.
- Regional disparities with South, Midwest, Northeast, and West showing higher rates.
- Demographic gaps affecting women and minorities disproportionately.
- Survey design features like `Question` and `Topic` are significant in classification.
- Best model: Manual feature selection with Random Forest achieving 92% accuracy and F1 = 1.00 for Cognitive Decline.
- SMOTE improves minority-class recall with a slight trade-off in overall accuracy.

### Recommendations

1. Integrate culturally sensitive, region-specific screening into primary care.
2. Prioritise caregiving support in rural and low-income communities.
3. Standardise and improve survey instrument design for public-health data collection.
4. Use data-driven models for proactive, equitable resource allocation.
5. Track post-pandemic cognitive trends longitudinally.

### Requirements

- Python 3.x
- Libraries: pandas, numpy, matplotlib, seaborn, scikit-learn, imbalanced-learn

### Usage

Run the notebook cells in order to reproduce the analysis. Ensure the dataset CSV is in the same directory or update the path accordingly.

### License

This work is based on the published research paper. Please cite appropriately.