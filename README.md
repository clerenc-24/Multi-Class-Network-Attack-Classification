# Multi-Class Network Intrusion Detection System

## 1. Introduction
Modern networks generate high-dimensional traffic data that can be used to detect intrusions and cyber-attacks.  
This project builds a **multi-class network attack classifier** using the [MachineLearningCVE](https://canvas.elte.hu/courses/57936/files/4066824/download?wrap=1) dataset - a labeled dataset containing both benign traffic and multiple attack types.  

The main objectives are to implement, evaluate, and compare multiple supervised models, explore feature engineering, and perform hyperparameter tuning to improve performance.

---

## 2. Objectives

- Perform **Exploratory Data Analysis (EDA)** on high-dimensional network traffic data.  
- Engineer features and prepare data for machine learning.  
- Implement **multi-class classification** using several ML algorithms.  
- Apply **Monte-Carlo Cross-Validation (MCCV)**.  
- Conduct **hyperparameter tuning** using GridSearchCV or RandomizedSearchCV.  
- Compare models using **accuracy, macro-F1, per-class recall**, and other metrics.  
- Present results professionally with **plots and tables**.

---

## 3. Dataset Description
The dataset consists of multiple CSV files extracted from PCAP network captures collected during several days of simulated attacks.  

### Key Information:
- Each row represents a network flow with features such as:
  - Packet length statistics
  - Flow duration
  - Byte/packet counts
  - Timing features
  - TCP flag counters
- **Target variable:** Label  
- Example labels:
  - BENIGN
  - DoS Hulk, DoS Slowloris, DoS GoldenEye
  - DDoS
  - PortScan
  - Web Attack (SQL Injection, XSS)
  - BruteForce (FTP/SSH)
  - Bot
  - Infiltration

> Related labels are grouped into **attack families**: DoS, DDoS, PortScan, WebAttack, BruteForce, Botnet, Infiltration, and BENIGN.

---

## 4. Tasks Overview

### Task 1 — Load and Inspect the Dataset
- Load CSV files from the ZIP archive and concatenate into a single DataFrame.  
- Display:
  - Dataset shape
  - Feature list
  - Value counts for attack types  
- Convert attack labels into attack families.  

**Deliverable:** Summary of dataset, sample rows, label distribution plot.

---

### Task 2 — Exploratory Data Analysis (EDA)
Perform comprehensive EDA:

#### 2.1 Descriptive Statistics
- Summary statistics: mean, median, standard deviation  
- Missing value analysis  
- Outlier detection (boxplots, IQR method)

#### 2.2 Univariate Analysis
- Distribution of key traffic features (histograms)  
- Correlation matrix, heatmaps, and causality analysis

#### 2.3 Multivariate Analysis
- Pairplots for a subset of features  
- PCA visualization (2D/3D)  
- Discussion on separability of attack families  

**Deliverable:** Figures and interpretation of patterns in the data.

---

### Task 3 — Feature Engineering
- Cleaning: handle ∞ and NaN values  
- Scaling: StandardScaler or MinMaxScaler  
- Feature selection: Sequential Forward/Backward or Bidirectional selection  
- Dimensionality reduction: PCA (retain 95% variance or fixed k)

**Deliverable:** Explanation and justification of engineered features.

---

### Task 4 — Multi-Class Classification Models
- Implement at least three classifiers:
  - Decision Tree
  - Naive Bayes
  - k-NN
- Evaluate models with:
  - Accuracy
  - Macro-F1 score
  - Per-class recall

**Deliverable:** Comparison table and discussion of strengths and weaknesses.

---

### Task 5 — Monte-Carlo Cross-Validation (MCCV)
- Set up MCCV with multiple iterations (e.g., 100–200)  
- For each iteration:
  - Random train/test split (70%/30%)  
  - Train classifier and record metrics  

**Deliverable:**
- Plots showing model performance across iterations  
- Statistical comparison of model stability  

---

### Task 6 — Hyperparameter Tuning
- Select best-performing model  
- Tune using:
  - GridSearchCV  
  - RandomizedSearchCV (preferred for large search spaces)  

**Deliverable:**
- Best hyperparameters  
- Comparison of base model vs tuned model  
- Improved evaluation metrics

---

## 5. Technologies Used
- Python (Pandas, NumPy, Scikit-learn, Matplotlib, Seaborn)  
- Jupyter Notebook  
- Machine Learning algorithms: Decision Tree, Naive Bayes, k-NN  
- PCA, feature selection methods  

---

## 6. Results
- Multi-class classifier evaluated on **accuracy, macro-F1, per-class recall**  
- Visualizations for EDA, feature importance, and model performance  
- Hyperparameter tuning improved model stability and accuracy  

---

## 7. How to Run
1. Clone this repository:
```bash
git clone https://github.com/yourusername/Network-Intrusion-Detection.git
