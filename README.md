# 🫀 Heart Disease Prediction: A Decision Tree Approach

---

## 📌 Project Overview
Cardiovascular diseases (CVDs) are the leading cause of death globally. Early detection is critical for effective treatment. 

This project utilizes **Machine Learning** to build a diagnostic tool capable of predicting the presence of heart disease based on patient medical attributes. By employing a **Decision Tree Classifier** and optimizing it via **Hyperparameter Tuning**, this model provides interpretable and accurate predictions.

**Objectives:**
* Analyze clinical data to identify key risk factors.
* Build a predictive model to classify patients as "Healthy" or "Disease Detected".
* Visualize the decision-making process of the algorithm.

---

## 📂 The Dataset
The model is trained on the **Cleveland Heart Disease Dataset** (UCI Machine Learning Repository). It consists of 303 patient records with 14 distinct features.

| Attribute | Description | Type |
| :--- | :--- | :--- |
| **age** | Age in years | Numerical |
| **sex** | 1 = Male; 0 = Female | Categorical |
| **cp** | Chest Pain Type (0: Typical Angina, 1: Atypical, 2: Non-anginal, 3: Asymptomatic) | Categorical |
| **trestbps** | Resting Blood Pressure (mm Hg) | Numerical |
| **chol** | Serum Cholestoral in mg/dl | Numerical |
| **fbs** | Fasting Blood Sugar > 120 mg/dl (1 = True) | Categorical |
| **restecg** | Resting ECG results (0, 1, 2) | Categorical |
| **thalach** | Maximum Heart Rate Achieved | Numerical |
| **exang** | Exercise Induced Angina (1 = Yes) | Categorical |
| **oldpeak** | ST depression induced by exercise relative to rest | Numerical |
| **slope** | Slope of the peak exercise ST segment | Categorical |
| **ca** | Number of major vessels (0-3) colored by fluoroscopy | Numerical |
| **thal** | Thalassemia (1: Fixed defect, 2: Normal, 3: Reversible defect) | Categorical |
| **target** | **Diagnosis** (1 = Disease, 0 = No Disease) | Target |

---

## 🛠️ Technologies Used

* Pandas: Data manipulation and cleaning.

* NumPy: Numerical operations.

* Matplotlib / Seaborn: Heatmaps, Bar charts, and Tree visualization.

* Scikit-Learn: Machine Learning implementation (DecisionTree, GridSearchCV).

  ---

  
## ⚙️ Methodology

### 1. Data Preprocessing
* **Cleaning:** Checked for null values and removed duplicate entries to prevent model bias.
* **Encoding:** Applied **One-Hot Encoding** to nominal categorical variables (`cp`, `restecg`, `thal`) to ensure the model treats them mathematically correctly without assuming a hierarchy.

### 2. Model Selection
* Algorithm: **Decision Tree Classifier**.
* Why? Decision Trees are highly interpretable and mimic human decision-making logic.

### 3. Hyperparameter Tuning
* To prevent **Overfitting** (where the model memorizes the data instead of learning patterns), I used **GridSearchCV**.
* **Optimized Parameters:**
    * `max_depth`: Controlled the vertical growth of the tree.
    * `min_samples_split`: Ensured nodes have enough data before splitting.
    * `criterion`: Tested both 'Gini Impurity' and 'Entropy'.

---

## 📊 Model Performance

The model was evaluated on a held-out Test Set (30% of data).

* Accuracy: ~81.32%

* Precision: High precision indicates a low False Positive rate.

* Recall: High recall indicates a low False Negative rate (crucial in healthcare).

---

## 🔍 Key Findings

Using Feature Importance analysis, the model identified the following as the strongest predictors of heart disease:

* Chest Pain Type (cp): Specifically asymptomatic pain.
  
* Thalassemia (thal): Reversible defects were highly correlated with disease.

* Number of Major Vessels (ca): Patients with fewer visible vessels often had higher risk.

* Max Heart Rate (thalach): Lower max rates during stress tests indicated issues.
