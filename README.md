This project uses Orange Data Mining to automate and improve loan eligibility prediction for the banking industry. The system processes both structured tabular data (CSV) and unstructured financial document images to determine whether an applicant is eligible for a loan
## Workflow Pipelines Explained

### 1. Data Analysis Pipeline
![Data Analysis Workflow](analize%20the%20dataframe.png)
This pipeline focuses on Exploratory Data Analysis (EDA)[cite: 1]. It loads the raw dataset and connects it to visualization widgets—**Distributions**, **Feature Statistics**, **Correlations**, **Scatter Plot**, **FreeViz**, and **Rank**—to inspect feature distributions, detect relationships, and rank attribute importance[cite: 1].

---

### 2. Data Modeling Pipeline
![Data Modeling Workflow](the%20modiling%20part.png)
This pipeline cleans, trains, and evaluates multiple machine learning models:
* **Preprocessing:** Cleans data via **Impute** (fills missing values)[cite: 1], **Preprocess** (normalizes values)[cite: 1], and **Outliers** (removes anomalous entries)[cite: 1].
* **Sampling & Training:** Uses **Data Sampler**[cite: 1] to split clean data across multiple models (**kNN**, **Tree**, **SVM**, **Random Forest**, **Naive Bayes**, and **Neural Network**).
* **Evaluation & Saving:** Compares performance using **Test and Score** and **Confusion Matrix**[cite: 1], then exports the top model using **Save Model**[cite: 1].

---

### 3. Data Prediction Pipeline
![Data Prediction Workflow](the%20prediction%20part.png)
This inference pipeline loads new, unseen applicant data alongside the pre-trained model via **Load Model**[cite: 1]. The **Predictions** widget outputs real-time loan approval decisions (`Y` / `N`), verified using a **Confusion Matrix**[cite: 1].
