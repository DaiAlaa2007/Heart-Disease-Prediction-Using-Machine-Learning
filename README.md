# ❤️ HeartGuard

### Heart Disease Prediction Using Machine Learning

HeartGuard is a Machine Learning project designed to predict the likelihood of heart disease using patient clinical and biometric data.

The project compares several classical Machine Learning classification algorithms and evaluates their performance using **Accuracy** and **Recall**, with a particular focus on detecting actual heart disease cases and reducing False Negatives.

---

## 📌 Project Overview

HeartGuard follows a complete Machine Learning pipeline:

**Data Collection → Data Preprocessing → Exploratory Data Analysis → Feature Encoding → Train/Test Split → Feature Scaling → Model Training → Model Evaluation → Deployment**

The project uses the **UCI Heart Disease Dataset** and focuses on binary classification:

* `0` → Healthy
* `1` → Heart Disease

---

## 📊 Dataset

The dataset contains patient clinical and biometric features such as:

* Age
* Sex
* Chest Pain Type
* Resting Blood Pressure
* Cholesterol
* Fasting Blood Sugar
* Resting ECG
* Maximum Heart Rate
* Exercise-Induced Angina
* ST Depression
* Slope
* Number of Major Vessels
* Thalassemia

### Data Preprocessing

The following preprocessing steps were performed:

* Removed duplicate records.
* Checked for missing values.
* Detected cholesterol outliers using the IQR method.
* Preserved detected outliers because extreme physiological values may represent genuine medical variability.
* Applied One-Hot Encoding to categorical features.
* Used `drop_first=True` to avoid redundant dummy variables.
* Split the data into **80% training** and **20% testing**.
* Used stratification to preserve the target-class distribution.
* Applied `StandardScaler` to the training and test features where scaling was appropriate.

---

## 🔍 Exploratory Data Analysis

Several visualizations were used to understand the dataset, including:

* Heart Disease Target Distribution
* Age Distribution
* Age vs. Heart Disease
* Chest Pain Type vs. Heart Disease
* Numerical Feature Correlation Heatmap

---

# 🤖 Machine Learning Models

Five classical classification models were evaluated:

1. Logistic Regression
2. Decision Tree Classifier
3. Support Vector Machine (SVM)
4. K-Nearest Neighbors (KNN)
5. Gaussian Naive Bayes

K-Means clustering was also explored as an unsupervised learning approach.

---

## 1. Logistic Regression

Logistic Regression was used as a binary classification model.

It produces a probability between **0 and 1** using the Sigmoid function, which can then be converted into a class prediction using a decision threshold.

### Results

* **Accuracy:** 85.2%
* **Recall:** 87.9%

Logistic Regression was selected as the model used by the application because it achieved the highest Recall among the evaluated classification models and provides probability outputs that can be used for the application's risk score.

---

## 2. Decision Tree Classifier

The Decision Tree classifies patients through hierarchical feature splits and threshold-based conditions.

For example:

```text
Is Age > 50?
       ↓
   Yes / No
       ↓
Next Feature
```

Decision Trees are highly interpretable, but complex trees can become susceptible to overfitting, particularly on smaller clinical datasets.

### Results

* **Accuracy:** 78.7%
* **Recall:** 78.8%

---

## 3. Support Vector Machine (SVM)

SVM attempts to construct a decision boundary, or hyperplane, that separates the healthy and heart-disease classes while maximizing the margin between them.

### Results

* **Accuracy:** 83.6%
* **Recall:** 84.8%

SVM was used as a strong benchmark model against Logistic Regression.

---

## 📈 Model Comparison

| Model               |  Accuracy |    Recall |
| ------------------- | --------: | --------: |
| Logistic Regression | **85.2%** | **87.9%** |
| Decision Tree       |     78.7% |     78.8% |
| SVM                 |     83.6% |     84.8% |
| KNN                 |     77.0% |     75.8% |
| Naive Bayes         |     80.3% |     84.8% |

### Evaluation Metrics

**Accuracy** measures the overall proportion of correct predictions.

**Recall (Sensitivity)** measures how many of the actual positive heart disease cases were correctly identified by the model.

Recall is particularly important in this project because a **False Negative** represents a patient who actually has heart disease but is predicted as healthy.

---

## 🧮 Classification Report

The Logistic Regression model was further evaluated using:

* Precision
* Recall
* F1-score
* Support
* Accuracy

A confusion matrix was also generated to visualize:

* True Positives (TP)
* True Negatives (TN)
* False Positives (FP)
* False Negatives (FN)

---

# 🌐 HeartGuard Web Application

The selected Logistic Regression model is used for real-time inference in the HeartGuard Streamlit application.

The application provides a risk score based on the model's probability output.

The project includes different user input levels, allowing basic inputs for standard users and more detailed clinical inputs for specialists.

---

## 🛠️ Technologies Used

* Python
* Pandas
* NumPy
* Matplotlib
* Seaborn
* Scikit-learn
* Streamlit
* Google Colab
* GitHub

---

## 📂 Project Structure

```text
HeartGuard/
│
├── HeartDiseaseTrain-Test.csv
├── HeartGuard.ipynb
├── app.py
├── README.md
└── requirements.txt
```

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone YOUR_GITHUB_REPOSITORY_URL
cd HeartGuard
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the Streamlit application

```bash
streamlit run app.py
```

---

## ⚠️ Disclaimer

HeartGuard is an educational Machine Learning project and is **not a medical diagnostic tool**.

Predictions generated by the application should not replace professional medical evaluation or diagnosis.

---

## 👥 Project

**HeartGuard**
Machine Learning Project

Developed using classical Machine Learning techniques for educational and predictive analytics purposes.

