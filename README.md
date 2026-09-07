This project uses Orange Data Mining to automate and improve loan eligibility prediction for the banking industry. The system processes both structured tabular data (CSV) and unstructured financial document images to determine whether an applicant is eligible for a loan
# 🏦 Loan Data Mining Project (Orange)

An end-to-end Machine Learning project implemented in **Orange Data Mining** to classify and predict loan eligibility using structured financial data.

---

## 📊 Workflow Pipelines Explained

### 1. Data Analysis Pipeline
![Data Analysis Workflow](analize%20the%20dataframe.png)

This pipeline handles Exploratory Data Analysis (EDA). It streams raw dataset attributes into visualization widgets—**Distributions**, **Feature Statistics**, **Correlations**, **Scatter Plot**, **FreeViz**, and **Rank**—to evaluate attribute spreads, linear dependencies, and target separation.

---

### 2. Data Modeling Pipeline
![Data Modeling Workflow](the%20modiling%20part.png)

This pipeline cleans, trains, and benchmark-tests machine learning models:
* **Data Cleaning & Normalization:** Processes raw inputs using **Impute** (missing value handling), **Preprocess** (scaling), and **Outliers** (anomalous data filtering).
* **Sampling & Model Training:** Splits clean inliers via **Data Sampler** to train 6 distinct algorithms: **kNN**, **Tree**, **SVM**, **Random Forest**, **Naive Bayes**, and **Neural Network**.
* **Evaluation & Export:** Evaluates performance via **Test and Score** alongside a **Confusion Matrix**, exporting the optimal trained model via **Save Model**.

---

### 3. Data Prediction Pipeline
![Data Prediction Workflow](the%20prediction%20part.png)

This operational inference pipeline feeds unseen applicant data into the pre-trained classifier via **Load Model**. The **Predictions** widget outputs loan approval classifications (`Y` / `N`), verified using a **Confusion Matrix**.

---

## 🔍 Exploratory Data Analysis (EDA) Visual Proofs

### 1. Feature Statistics & Dataset Integrity
![Feature Statistics Output](statistical%20info.png)

* **Statistical Distributions:** Tracks distributions, mean/median values, and dispersion across numerical metrics (`Applicant_Income`, `Loan_Amount`, `Term`) and categorical descriptors (`Credit_History`, `Area`, `Education`).
* **Missing Value Analysis:** Identifies missing entries across attributes (e.g., `Credit_History` missing 25 values / 7%, `Term` missing 7 values / 2%), establishing the operational baseline for data imputation.

---

### 2. Linear Correlation Analysis
![Feature Correlations Output](the%20coorelation%20.png)

* **Income vs. Loan Magnitude:** Displays a strong positive linear correlation (**+0.542**) between `Applicant_Income` and `Loan_Amount`.
* **Coapplicant Contribution:** Identifies a secondary positive relation (**+0.197**) between `Coapplicant_Income` and `Loan_Amount`.
* **Parameter Independence:** Shows negligible correlation between `Term` and applicant income metrics (`-0.012` to `-0.082`).

---

### 3. Class Balance Distribution
![Target Class Distribution](the%20distrebution.png)

* **Target Equality:** Demonstrates balanced distribution across the binary target `Status` (~192 samples for both `N` and `Y`), ensuring model training remains unskewed by class imbalance.

---

### 4. Bivariate Scatter Plot & Outlier Detection
![Applicant Income Scatter Plot](the%20scater%20plot.png)

* **Feature Interaction:** Maps `Applicant_Income` across `Gender` categories colored by target loan outcome.
* **Outlier Isolation:** Identifies extreme income data points ($>8 \times 10^6$), validating the downstream **Outliers** filtering node.

---

## 📈 Model Benchmark & Experimental Proofs

### 1. Cross-Validation Results Table
![Orange Test and Score Table](models%20results.png)

* **Random Forest** achieved top overall performance across **AUC (0.721)**, **Classification Accuracy (0.646)**, and **F1-Score (0.647)**.
* **Support Vector Machine (SVM)** delivered the highest Precision (**0.670**) and **MCC (0.312)**.

---

### 2. Prediction Confusion Matrix
![Orange Confusion Matrix Output](predection%20result.png)

* **Evaluation Scale:** Tested across 246 sample records (130 actual non-approvals `N`, 116 actual approvals `Y`).
* **Classification Accuracy:** Successfully classified **72 True Negatives** (`N`) and **83 True Positives** (`Y`).
