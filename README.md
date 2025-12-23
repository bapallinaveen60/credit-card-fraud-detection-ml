# credit-card-fraud-detection-ml
end to end machine learning framework for credit card fraud detection using imbalance dada handling and advanced evaluation matrics
# Credit Card Fraud Detection Using Machine Learning

## 📌 Project Description
Credit card fraud detection is a critical and challenging problem in the financial industry due to the rapid growth of digital transactions and the extremely imbalanced nature of fraud data. Fraudulent transactions represent only a very small fraction of all transactions, which makes traditional machine learning models biased toward predicting the majority (legitimate) class and renders accuracy an unreliable evaluation metric.

This project presents an end-to-end, industry-aligned machine learning framework for detecting fraudulent credit card transactions. The primary objective is to accurately identify fraud while minimizing false positives, which is crucial for reducing financial losses and improving customer trust in real-world systems.

The project emphasizes correct data handling, proper treatment of class imbalance, and business-aware evaluation metrics, making it suitable for real-world deployment scenarios.

---

## 📊 Dataset Overview
The study uses a real-world credit card transaction dataset containing **284,807 transactions**, out of which only **0.17% are fraudulent**. Due to confidentiality and privacy constraints, the original transaction features have been anonymized and transformed using Principal Component Analysis (PCA).

**Dataset characteristics:**
- PCA-transformed features: `V1`–`V28`
- Additional features:
  - `Amount` – transaction amount
  - `Time` – time elapsed between transactions
- Target variable:
  - `Class` (0 = Legitimate, 1 = Fraud)

The severe class imbalance in the dataset necessitates specialized preprocessing and evaluation strategies.

---

## 🔍 Exploratory Data Analysis (EDA)
Exploratory Data Analysis was conducted to gain insights into transaction behavior and data distribution. The EDA phase focused on:
- Understanding feature distributions
- Analyzing transaction amounts and temporal patterns
- Visualizing class imbalance
- Identifying the need for imbalance-aware modeling techniques

The analysis confirmed that fraudulent transactions are extremely rare, motivating the use of stratified sampling and oversampling techniques during model development.

---

## ⚙️ Data Preprocessing and Imbalance Handling
To ensure reliable model performance, the following preprocessing steps were applied:

- Stratified train–test split to preserve the original fraud ratio in the test set
- Standardization of the `Amount` feature
- PCA-transformed features were retained without modification
- **Synthetic Minority Over-sampling Technique (SMOTE)** was applied **only on the training data** to avoid data leakage

This approach resulted in a balanced training dataset suitable for effective model learning while keeping the test data representative of real-world conditions.

---

## 🤖 Machine Learning Models
Three machine learning models were trained and evaluated:

### 1. Logistic Regression
- Used as a baseline model
- Achieved high fraud recall
- Generated a large number of false positives

### 2. Random Forest
- Reduced false positives compared to Logistic Regression
- Slight reduction in fraud recall
- Provided better balance between precision and recall

### 3. XGBoost
- Advanced gradient boosting model
- Achieved the best overall performance
- Provided strong balance between fraud detection and false alarm reduction
- Selected as the final model for deployment consideration

---

## 📈 Model Evaluation Strategy
Due to the imbalanced nature of the dataset, model performance was evaluated using metrics that better reflect real-world business impact:

- Confusion Matrix
- Precision, Recall, and F1-score
- ROC–AUC
- Precision–Recall curves

Special emphasis was placed on **fraud recall** and **false positive rates**, as these directly influence financial risk and operational costs.

---

## 🏆 Results Summary
The comparative analysis showed that:

- Logistic Regression achieved high recall but suffered from excessive false positives
- Random Forest reduced false alarms but slightly reduced recall
- **XGBoost achieved the best overall performance**, with:
  - ROC–AUC ≈ **0.97**
  - Fraud Recall ≈ **0.82**
  - Precision ≈ **0.85**
  - Minimal false positives

This balance makes XGBoost the most suitable model for real-world fraud detection systems.

---

## 🚀 Key Contributions
- End-to-end fraud detection pipeline
- Proper handling of highly imbalanced data
- Business-oriented evaluation framework
- Comparative analysis of classical and advanced ML models
- Deployment-ready modeling approach

---

## 🛠️ Tools & Technologies
- Python
- Scikit-learn
- XGBoost
- imbalanced-learn (SMOTE)
- Pandas, NumPy
- Matplotlib, Seaborn
- Jupyter Notebook

---

## 🔮 Future Enhancements
- Threshold tuning for cost-sensitive optimization
- Real-time fraud detection pipeline
- API-based deployment (FastAPI)
- Cost-aware and anomaly detection models

---

## 👤 Author
**Baipilli Naveen**  
M.Tech Climate Change, IIT Hyderabad
