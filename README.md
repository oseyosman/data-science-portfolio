# Applied Data Science & Machine Learning Portfolio

[![Python](https://img.shields.io/badge/Python-3.10%2B-blue?logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow&logoColor=white)](https://tensorflow.org/)
[![Pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)](https://pandas.pydata.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?logo=jupyter&logoColor=white)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

A curated collection of end-to-end data science, statistical analysis, and machine learning projects developed during graduate coursework in **IT 540: Applied Data Science** at **Walsh College**.

This repository progresses from classical supervised statistical modeling to deep artificial neural networks, unsupervised clustering, and an extensive healthcare capstone analysis.

---

## 🗂️ Curriculum & Project Overview

| # | Project / Module | Core Techniques & Algorithms | Key Libraries | Dataset | Highlights & Key Takeaways |
| :---: | :--- | :--- | :--- | :--- | :--- |
| 🎓 | [**Final Capstone Project**](./Final%20Project/) | **EDA, K-Means Clustering ($k=4$), Multiple Linear Regression** | `pandas`, `scikit-learn`, `seaborn`, `matplotlib` | Michigan Dept. of Health ($N=367$ cities) | Quantified municipal prenatal care disparities; identified 4 risk tiers; $R^2 = 0.214$. |
| 01 | [**Assignment 1: Linear Regression**](./Assignment%201/) | **Simple & Multiple Linear Regression, Residual Diagnostics** | `pandas`, `numpy`, `scikit-learn`, `matplotlib` | Continuous tabular dataset | Parametric model fitting, slope/intercept interpretation, and line-of-best-fit evaluation. |
| 02 | [**Assignment 2: Random Forest**](./Assignment%202/) | **Random Forest Classifier, Decision Trees, Gini Impurity** | `scikit-learn`, `pandas`, `numpy` | UCI Cleveland Heart Disease ($N=303$) | Multi-factor clinical diagnostic classification; ranked clinical indicators by feature importance. |
| 03 | [**Assignment 3: Neural Networks**](./Assignment%203/) | **Deep Multi-Layer Perceptrons (MLP), Batch Norm, Dropout** | `tensorflow`, `keras`, `scikit-learn` | Lichess Large Game Dataset ($100,000$ matches) | Deep architecture for tabular game outcome classification; loss convergence and regularization. |
| 04 | [**Assignment 4: Clustering & PCA**](./Assignment%204/) | **K-Means Clustering, PCA, KNN Classifier, Elbow Analysis** | `scikit-learn`, `matplotlib`, `pandas` | UCI Glass Identification Dataset | Chemical composition clustering; high-to-low dimensional projection and centroid distance analysis. |

---

## 🌟 Featured Capstone: Analysis of Michigan Birth Outcomes & Prenatal Care Disparities

> 📁 **Full details and written report**: See the [Final Project Directory](./Final%20Project/) and [Executive Summary Report](./Final%20Project/Executive_Summary_Report.md).

### Problem Statement
Prenatal healthcare access directly influences maternal and infant mortality rates. This project analyzes whether demographic composition across Michigan municipalities can predict rates of **inadequate prenatal care** (based on the Kotelchuck Index).

### Key Findings & Visuals
* **Demographic Disparities**: Cities with higher percentages of African American residents exhibited elevated rates of inadequate prenatal care ($r = 0.50$).
* **Unsupervised Clustering ($k=4$)**: Identified distinct municipal tiers, separating well-resourced suburbs from structurally underfunded urban health corridors.
* **Supervised Predictive Modeling**: Multiple Linear Regression achieved $R^2 = 0.214$ and $\text{RMSE} = 8.07\%$, demonstrating significant predictive signal while highlighting the need to include broader socioeconomic variables (income, transit access, clinic density).

<p align="center">
  <img src="Final%20Project/assets/correlation_heatmap.png" width="48%" alt="Correlation Heatmap"/>
  <img src="Final%20Project/assets/cluster_analysis.png" width="48%" alt="K-Means Clusters"/>
</p>

<p align="center">
  <img src="Final%20Project/assets/regression_performance.png" width="96%" alt="Regression Performance"/>
</p>

---

## 🔬 Coursework Modules Breakdown

### 1. [Assignment 1: Linear Regression Analysis](./Assignment%201/Assignment1_YildizOsman.ipynb)
* Built baseline statistical regression models to predict continuous target variables.
* Implemented scatter plotting, fitted regression trend lines, calculated Mean Squared Error (MSE), and analyzed residuals to validate linear assumptions.

### 2. [Assignment 2: Heart Disease Diagnosis with Random Forest](./Assignment%202/Assignment2_Template_YildizOsman.ipynb)
* Applied ensemble tree methods to the benchmark **UCI Cleveland Clinic Heart Disease dataset**.
* Preprocessed categorical and continuous biometric markers (cholesterol, resting blood pressure, fluoroscopy vessels, thallium stress results).
* Trained and evaluated a **Random Forest Classifier**, preventing overfitting through ensemble bagging and extracting feature importance metrics.

### 3. [Assignment 3: Deep Artificial Neural Networks (ANN)](./Assignment%203/Assignment3_Template_YildizOsman.ipynb)
* Architected a feed-forward Multi-Layer Perceptron using **TensorFlow & Keras** on a 100,000-row game outcome dataset.
* Handled large-scale tabular normalization using `StandardScaler` and `PowerTransformer`.
* Implemented hidden layers with `ReLU` activations, `BatchNormalization`, and `Dropout` regularization to stabilize gradient descent and mitigate overfitting.

### 4. [Assignment 4: Unsupervised Clustering & PCA Dimensionality Reduction](./Assignment%204/Assignment4_Template_YildizOsman.ipynb)
* Uncovered latent groupings in material forensics using the **UCI Glass Identification dataset** (refractive index and elemental percentages: Na, Mg, Al, Si, K, Ca, Ba, Fe).
* Evaluated optimal cluster counts ($k$) using inertia elbow plots.
* Paired clustering with **K-Nearest Neighbors (KNN)** classification and **Principal Component Analysis (PCA)** for 2D visualization of high-dimensional physical properties.

---

## 🛠️ Tech Stack & Skills Demonstrated

* **Programming**: Python 3.10+
* **Data Manipulation & Analysis**: Pandas, NumPy
* **Data Visualization**: Matplotlib, Seaborn
* **Machine Learning**: Scikit-Learn (Linear Regression, Random Forest, K-Means, KNN, PCA, StandardScaler)
* **Deep Learning**: TensorFlow, Keras (Dense layers, Batch Normalization, Dropout)
* **Best Practices**: Reproducible workflows, exploratory data analysis, train-test splitting, cross-validation, and executive reporting.

---

## 🚀 Getting Started & Local Reproduction

### 1. Clone the repository
```bash
git clone https://github.com/oseyosman/data-science-portfolio.git
cd data-science-portfolio
```

### 2. Set up virtual environment
```bash
python3 -m venv venv
source venv/bin/activate    # On Windows: venv\Scripts\activate
pip install -r requirements.txt
```

### 3. Launch JupyterLab or Notebook
```bash
jupyter notebook
```
Navigate to any assignment notebook or the `Final Project/` folder to run the analyses interactively.

---

## 👤 Author

* **Osman Yildiz**
* Master's Student in Information Technology / Data Science — Walsh College
* GitHub: [@oseyosman](https://github.com/oseyosman)
* LinkedIn: [Osman Yildiz](https://linkedin.com)
