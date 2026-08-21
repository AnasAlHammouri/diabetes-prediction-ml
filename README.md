# 🩺 End-to-End Diabetes Prediction & Classification Pipeline

An end-to-end Supervised Machine Learning pipeline built to predict the onset of diabetes based on diagnostic measurements from the **Pima Indians Diabetes Database** (Kaggle).

---

## 📌 1. Project Overview & Objective
Diabetes is a chronic metabolic disease with significant global healthcare implications. Early and automated diagnostic screening helps medical professionals make faster interventions.

The core objective of this project is to:
- Conduct an in-depth **Exploratory Data Analysis (EDA)** on clinical attributes.
- Identify and handle **biologically impossible zero values** (hidden missing data).
- Train, tune, and evaluate **6 different classification algorithms**.
- Identify key physiological risk indicators influencing diabetes prediction.

---

## 📂 2. Repository Structure

* **`diabetes-prediction.ipynb`** : Main Jupyter Notebook (EDA, Preprocessing, Modeling)
* **`diabetes.csv`** : Original Dataset
* **`requirements.txt`** : Project dependencies and library versions
* **`README.md`** : Project documentation and summary

---

## 📊 3. Dataset Description
The dataset consists of **768 observations** and **9 clinical attributes**:

| Feature | Description | Range / Notes |
| :--- | :--- | :--- |
| `Pregnancies` | Number of times pregnant | 0 – 17 |
| `Glucose` | Plasma glucose concentration (2 hours in OGTT) | Hidden missing values present as 0 |
| `BloodPressure` | Diastolic blood pressure (mm Hg) | Hidden missing values present as 0 |
| `SkinThickness` | Triceps skinfold thickness (mm) | Hidden missing values present as 0 |
| `Insulin` | 2-Hour serum insulin (mu U/ml) | Hidden missing values present as 0 |
| `BMI` | Body mass index (weight in kg / (height in m)^2) | Hidden missing values present as 0 |
| `DiabetesPedigreeFunction` | Genetic score / family history likelihood | Continuous metric |
| `Age` | Age in years | 21 – 81 |
| **`Outcome`** *(Target)* | Class variable (0 = Non-Diabetic, 1 = Diabetic) | Binary classification |

---

## ⚙️ 4. Data Preprocessing & Methodology

### A. Missing Value Detection & Imputation
In clinical datasets, zero values in physiological indicators (e.g., Blood Pressure = 0 or Glucose = 0) represent unrecorded/missing observations rather than true physiological zeros.
- **Identified Zeros:** Insulin (374), SkinThickness (227), BloodPressure (35), BMI (11), Glucose (5).
- **Strategy:** Replaced zeros with `NaN` and applied **Median Imputation** across respective features to preserve distribution integrity without skewing due to outliers.

### B. Exploratory Data Analysis (EDA)
- **Histograms:** Analyzed feature skewness and normal distributions post-imputation.
- **Boxplots:** Detected extreme values across clinical markers (e.g., Insulin spikes).
- **Correlation Matrix (Heatmap):** 
  - `Glucose` and `BMI` demonstrated the strongest positive correlation with the target `Outcome`.
  - `Age` and `Pregnancies` showed moderate collinearity.

---

## 🤖 5. Machine Learning Models & Evaluation

The following models were trained and benchmarked using train-test split validation:

1. **Logistic Regression** (Baseline linear classifier)
2. **Random Forest Classifier** (Ensemble tree-based method)
3. **Support Vector Classifier (SVC)** (Kernel-based decision boundaries)
4. **Decision Tree Classifier**
5. **K-Nearest Neighbors (KNN)**
6. **Gaussian Naive Bayes (GaussianNB)**

### Evaluation Metrics:
- **Accuracy Score**
- **Precision, Recall, & F1-Score** (Crucial for medical diagnosis to minimize false negatives)
- **Confusion Matrix & Classification Report**

---

## 💡 6. Key Insights & Takeaways
1. **Glucose Levels:** The single strongest indicator of diabetes risk in the dataset.
2. **BMI & Adiposity:** Elevated BMI significantly increases positive classification probability.
3. **Data Quality Impact:** Imputing hidden zeros improved convergence and prevented models from learning biased zero-value patterns.

---

## 🚀 7. Installation & Usage

1. **Clone the repository:**
   ```bash
   git clone [https://github.com/AnasAlHammouri/diabetes-prediction-ml.git](https://github.com/AnasAlHammouri/diabetes-prediction-ml.git)
   cd diabetes-prediction-ml

👤 Author
Anas Al-Hammouri

Connect on [LinkedIn] (https://www.linkedin.com/in/anas-al-hammouri-941a64421/)

   
   git clone https://github.com/AnasAlHammouri/diabetes-prediction-ml.git
   cd diabetes-prediction-ml
