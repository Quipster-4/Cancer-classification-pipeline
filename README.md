# 🧬 TCGA Cancer Classification Pipeline

![Spark](https://img.shields.io/badge/Apache%20Spark-FDEE21?style=flat&logo=apachespark&logoColor=black) ![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white) ![Colab](https://img.shields.io/badge/Google_Colab-F9AB00?style=flat&logo=googlecolab&logoColor=white)

A distributed machine learning pipeline built with **Apache Spark MLlib** to classify cancer types based on genomic expression data from The Cancer Genome Atlas (TCGA).

---

## 🚀 How to Run (One-Click Setup)

This project is optimized for **Google Colab**. Due to the large size of the dataset (1.5GB), I have implemented an automated setup script within the notebook.

**You do NOT need to manually download or upload any data.**

1. Click the badge below to open the notebook:
   
   [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/Quipster-4/Cancer-classification-pipeline/blob/main/TCGA_Cancer_Classification.ipynb)

2. In the Colab menu, go to **Runtime** > **Run All**.
   * *The first cell will automatically detect that the data is missing, fetch it from the cloud backup, and unzip it into the workspace.*
   * *It will then install PySpark and execute the full pipeline.*

---

📊 Project Overview (Updated Objectives)

Key Objectives:

 - Process large-scale genomic datasets using Spark DataFrames.

 - Perform feature engineering and dimensionality reduction.

 - Optimize model performance using Cross-Validation and Grid Search.

 - Implement Ensemble Learning techniques to combine weak learners into a robust       predictor.

 --- 

🛠️ The Pipeline

1. Data Ingestion: Loading massive CSV datasets into Spark.

2. Preprocessing: Handling missing values and string indexing labels.

3. Feature Engineering:

 - VectorAssembler: Combining features into vector columns.

 - StandardScaler: Normalizing gene expression levels.

 - PCA (Principal Component Analysis): Reducing dimensionality to improve model performance and training speed.

4. Modeling & Optimization:

 - Multi-Model Training: Training Random Forest, Support Vector Machine (SVM), and Logistic Regression classifiers.

 - Hyperparameter Tuning: Using Cross-Validation (3-fold) to automatically find the best tree depth and count for the Random Forest model.

5. Ensemble Learning:

 - Implementing a Voting Classifier to combine predictions from all three models.

 - Using a custom Spark UDF to calculate the majority vote for robust final predictions.

6. Evaluation: Measuring and comparing performance (Accuracy) between individual models and the Ensemble.

---

"Due to computational constraints, hyperparameter tuning was restricted to a lightweight grid (1-5 trees). While this successfully demonstrated the automated tuning pipeline, the resulting model was underfitted. With more compute resources, increasing the tree count to 100+ would significantly improve accuracy."

---

## 📂 Repository Structure

```text
├── TCGA_Cancer_Classification.ipynb   # Main Spark notebook
├── random_forest_cancer_model/        # Pre-trained Spark model files
├── cancer_predictions/                # Sample output predictions (CSV/Parquet)
├── README.md                          # Project documentation
└── .gitignore                         # Configuration to exclude the 1.5GB raw data
