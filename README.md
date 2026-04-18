# 🧠 Cognitive Decline Analysis & Classification
### Exploratory Analysis of Factors Influencing Cognitive Decline Across Regional and Demographic Populations

> **Authors:** Ummid Salma Mulla · Pratibha M Patil · P. G. Sunitha Hiremath · Neha Tarannum Pendari  
> **Institution:** KLE Technological University, Vidyanagar, Hubballi, India  
> **Dataset Period:** 2015 – 2022 · **Records:** 284,142 rows × 31 columns

---

## 📌 Overview

This project conducts an **Exploratory Data Analysis (EDA)** and **multi-class classification** on publicly available CDC BRFSS data to uncover key determinants of cognitive decline among Alzheimer's patients across diverse demographic and geographic groups in the United States.

The study explores five major health domains:
- 🧠 **Cognitive Functioning**
- 🤝 **Caregiving Burden**
- 💬 **Mental Health**
- 🏥 **Chronic Conditions**
- 🌿 **Well-being**

---

## 📂 Project Structure

```
├── Alzheimer_Cognitive_Decline_Analysis.ipynb   ← Main Jupyter notebook
├── alzheimer_disease_and_healthy_aging_data.csv ← CDC BRFSS dataset (download separately)
├── README.md                                     ← You are here
│
├── figures/
│   ├── fig2_year_distribution.png
│   ├── fig3_2021_health_domains.png
│   ├── fig4_top10_locations.png
│   ├── fig5_cognitive_decline_trend.png
│   ├── fig6_top15_cognitive_decline_2019.png
│   ├── fig7_top10_questions_2019.png
│   ├── fig8_stratification_2019.png
│   ├── fig9_feature_importance.png
│   ├── fig10_correlation_feature_selection.png
│   ├── fig11_manual_feature_importance.png
│   ├── fig12_smote_distribution.png
│   ├── heatmap_cognitive_decline.png
│   └── model_comparison.png
```

---

## 📊 Dataset

| Property | Value |
|---|---|
| **Source** | CDC – Centers for Disease Control and Prevention |
| **Survey** | Behavioral Risk Factor Surveillance System (BRFSS) |
| **URL** | [data.cdc.gov – Alzheimer's Disease and Healthy Aging Data](https://data.cdc.gov/Healthy-Aging/Alzheimer-s-Disease-and-Healthy-Aging-Data/hfr9-rurv/data_preview) |
| **Period** | 2015 to 2022 |
| **Rows** | 284,142 |
| **Columns** | 31 |
| **Coverage** | 59 U.S. geographic regions |
| **Stratification** | Sex (~55%) · Race/Ethnicity (~45%) |

---

## ⚙️ Setup & Installation

### Prerequisites
- Python 3.8+
- Jupyter Notebook or JupyterLab

### Install Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn jupyter
```

### Run the Notebook

```bash
# 1. Clone or download this project folder
# 2. Download the dataset from the CDC link above and place it here:
#    alzheimer_disease_and_healthy_aging_data.csv

# 3. Launch Jupyter
jupyter notebook Alzheimer_Cognitive_Decline_Analysis.ipynb
```

> **Note:** If the CSV is not found, the notebook automatically generates a **synthetic demo dataset** with the same structure (284,142 rows) so every cell runs without errors.

---

## 🔬 Methodology

```
Raw CDC BRFSS Data
        │
        ▼
  Data Preprocessing
  ├─ Median imputation (numerical)
  ├─ Mode imputation (categorical)
  ├─ Label encoding
  └─ Duplicate removal
        │
        ▼
  Exploratory Data Analysis (EDA)
  ├─ Year-wise trends
  ├─ Geographic distribution
  ├─ Demographic stratification
  └─ Feature importance analysis
        │
        ▼
  Feature Selection
  ├─ Model A → Correlation-based (automated)
  └─ Model B → Domain-informed (manual)
        │
        ▼
  Classification (Random Forest · Logistic Regression)
  ├─ Model A  : Auto features
  ├─ Model B  : Manual features
  └─ Model C  : Manual + SMOTE
        │
        ▼
  Evaluation & Comparison
  (Accuracy · F1-Score · Confusion Matrix · Heatmaps)
```

---

## 🎯 Target Classes

The models classify each record into one of four health domains:

| Class | Description |
|---|---|
| 🤝 **Caregiving** | Caregiving burden and hours |
| 🧠 **Cognitive Decline** | Memory loss, functional limitations |
| 💬 **Mental Health** | Depression, anxiety, stress |
| 🏥 **Overall Health** | General health status |

---

## 📈 Key Results

### Model Performance Summary

| Model | Accuracy | Macro F1 | Notes |
|---|---|---|---|
| **A – Auto (Correlation)** | 73% | 0.56 | Over-predicts *Overall Health* |
| **B – Manual (Domain)** | **92%** | **0.92** | Best overall performance |
| **C – Manual + SMOTE** | 91% | 0.90 | Improved minority-class recall |

### Class-Level F1 Scores (Best Model – Manual Selection)

| Class | Precision | Recall | F1-Score |
|---|---|---|---|
| 🤝 Caregiving | 0.94 | 0.89 | **0.91** |
| 🧠 Cognitive Decline | 1.00 | 1.00 | **1.00** ✅ |
| 💬 Mental Health | 0.74 | 0.76 | **0.75** |
| 🏥 Overall Health | 0.93 | 0.94 | **0.94** |

---

## 🗺️ Key EDA Findings

- **2019 Spike** — Cognitive decline records peaked at ~4,773 entries in 2019, likely due to expanded awareness and improved reporting practices.
- **Regional Disparities** — The South, Midwest, Northeast, and West showed the highest rates of cognitive decline, linked to socioeconomic and infrastructure differences.
- **Demographic Gaps** — Women and minorities reported disproportionately higher rates of cognitive decline.
- **Survey Design Matters** — The `Question` and `Topic` features were the strongest predictors — outweighing geographic and demographic variables.
- **Post-Pandemic Effect** — Data trends show elevated cognitive stress and mental health challenges post-2020.

---

## 🧪 Models & Techniques

| Technique | Purpose |
|---|---|
| `RandomForestClassifier` | Primary classifier for all three models |
| `LogisticRegression` | Secondary classifier for comparison |
| `SMOTE` | Synthetic oversampling for class imbalance |
| `class_weight='balanced'` | Built-in imbalance correction |
| Correlation filtering | Automated feature selection (Model A) |
| Domain knowledge + EDA | Manual feature selection (Model B & C) |
| Heatmaps | Regional pattern visualization |
| Confusion matrix | Per-class performance breakdown |

---

## 📌 Important Findings

> **Manual feature selection outperformed automated correlation-based selection by ~19% in accuracy** (92% vs 73%). This underscores that domain expertise and contextual understanding of public-health data are critical for building reliable classification models.

> **Cognitive Decline achieved a perfect F1-score of 1.00** with manually selected features, indicating strong signal separability when the right features are chosen.

---

## 📚 References

Key references underpinning this work:

1. Alzheimer's Association (2024). *2024 Alzheimer's Disease Facts and Figures.*
2. Prince et al. (2015). *World Alzheimer Report 2015.*
3. Zhang et al. (2011). *Multimodal classification of AD.* NeuroImage.
4. Sarraf & Tofighi (2016). *DeepAD – CNNs for Alzheimer's classification.*
5. Anderson et al. (2009). *BRFSS cognitive health perceptions.* The Gerontologist.
6. Lundberg & Lee (2017). *SHAP – Unified model interpretation.* NeurIPS.
7. Mahajan et al. (2023). *COVID-19 impact on cognitive complaints.* Int. J. Geriatric Psychiatry.
8. Tang et al. (2024). *EHR-based AD prediction 7 years early.* Nature Aging.

> Full reference list available in the research paper.

---

## 🤝 Contributing

This is an academic research project. If you build on this work, please cite the original paper and the CDC BRFSS dataset.

---

## 📄 License

This project uses publicly available CDC data under open data principles. The code in this repository is available for academic and research use.

---

<div align="center">

Made with ❤️ at **KLE Technological University, Hubballi**

</div>
