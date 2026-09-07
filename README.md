This project uses Orange Data Mining to automate and improve loan eligibility prediction for the banking industry. The system processes both structured tabular data (CSV) and unstructured financial document images to determine whether an applicant is eligible for a loan
# 🏦 Loan Data Mining Project (Orange)

An end-to-end Machine Learning project implemented in **Orange Data Mining** to classify and predict loan eligibility using structured financial data and multi-modal document image embeddings.

---

## 📊 Workflow Pipelines Explained

### 1. Data Analysis Pipeline
![Data Analysis Workflow](analize%20the%20dataframe.png)

This pipeline focuses on Exploratory Data Analysis (EDA). It loads raw dataset records into visualization widgets—**Distributions**, **Feature Statistics**, **Correlations**, **Scatter Plot**, **FreeViz**, and **Rank**—to inspect feature spreads, detect feature relationships, and evaluate variable importance.

---

### 2. Data Modeling Pipeline
![Data Modeling Workflow](the%20modiling%20part.png)

This pipeline cleans, trains, and benchmark-tests machine learning models:
* **Data Cleaning & Normalization:** Processes raw inputs using **Impute** (missing value handling), **Preprocess** (scaling), and **Outliers** (anomalous data point filtering).
* **Sampling & Model Training:** Splits clean inliers via **Data Sampler** to train 6 distinct algorithms: **kNN**, **Tree**, **SVM**, **Random Forest**, **Naive Bayes**, and **Neural Network**.
* **Evaluation & Model Export:** Evaluates relative performance via **Test and Score** alongside a **Confusion Matrix**, exporting the optimal model using **Save Model**.

---

### 3. Data Prediction Pipeline
![Data Prediction Workflow](the%20prediction%20part.png)

This operational inference pipeline feeds unseen applicant data into the pre-trained classifier via **Load Model**. The **Predictions** widget outputs real-time loan approval classifications (`Y` / `N`), verified using a **Confusion Matrix**.

---

## 📈 Model Benchmark & Experimental Proofs

### 1. Cross-Validation Results Table
![Orange Test and Score Table](models%20results.png)

* **Random Forest** yielded the top overall performance across **AUC (0.721)**, **Classification Accuracy (0.646)**, and **F1-Score (0.647)**.
* **Support Vector Machine (SVM)** delivered the highest precision score (**0.670**) and **MCC (0.312)**.

---

### 2. Prediction Confusion Matrix
![Orange Confusion Matrix Output](predection%20result.png)

* **Sample Size:** Evaluated across 246 unseen evaluation records (130 actual non-approvals `N`, 116 actual approvals `Y`).
* **Correct Predictions:** Successfully classified **72 True Negatives** (`N`) and **83 True Positives** (`Y`).
