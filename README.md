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

## 📊 Project Overview

This project demonstrates the use of Big Data technologies to handle high-dimensional genomic data.

**Key Objectives:**
* Process large-scale genomic datasets using Spark DataFrames.
* Perform feature engineering and dimensionality reduction.
* Train a multi-class classification model to identify cancer types.

### 🛠️ The Pipeline

1.  **Data Ingestion:** Loading massive CSV datasets into Spark.
2.  **Preprocessing:** Handling missing values and string indexing labels.
3.  **Feature Engineering:**
    * **VectorAssembler:** Combining features into vector columns.
    * **StandardScaler:** Normalizing gene expression levels.
    * **PCA (Principal Component Analysis):** Reducing dimensionality to improve model performance and training speed.
4.  **Modeling:** Training a **Random Forest Classifier**.
5.  **Evaluation:** Measuring performance using Accuracy, Precision, and Recall.

---

## 📂 Repository Structure

```text
├── TCGA_Cancer_Classification.ipynb   # Main Spark notebook
├── random_forest_cancer_model/        # Pre-trained Spark model files
├── cancer_predictions/                # Sample output predictions (CSV/Parquet)
├── README.md                          # Project documentation
└── .gitignore                         # Configuration to exclude the 1.5GB raw data
