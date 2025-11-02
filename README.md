# 🛒 Customer Segmentation Using Clustering

## 📘 Project Overview
This project aims to perform **customer segmentation** for a supermarket to improve **membership card conversion rates** using unsupervised machine learning techniques.  
By identifying distinct customer groups based on demographic and spending behavior, marketing teams can target each segment effectively.

---

## 🎯 Problem Statement
Supermarkets struggle to increase membership card sign-ups because marketing campaigns often target all customers uniformly.  
This project focuses on **grouping customers** into distinct segments using clustering algorithms to enable:
- Personalized offers  
- Targeted marketing strategies  
- Better understanding of customer behavior  

---

## 📂 Dataset Information
- **Source:** Provided dataset (CSV file under `/data`)  
- **Records:** 200 customers  
- **Features Used:**  
  - `Age`  
  - `Gender` (encoded)  
  - `Annual Income`  
  - `Spending Score`  
- **Preprocessing Steps:**  
  - Missing value handling  
  - Label encoding  
  - Standard scaling  
  - Train–test split  

---

## ⚙️ Workflow Summary
1. **Exploratory Data Analysis (EDA)**  
   - Distribution and relationships between features  
   - Correlation heatmap and pairplots  
2. **Feature Scaling & Preparation**  
   - Data standardized using `StandardScaler`  
3. **Model Training & Evaluation**  
   - Algorithms used:  
     - KMeans  
     - Gaussian Mixture Model (GMM)  
     - Agglomerative Clustering  
     - DBSCAN  
4. **Model Comparison**  
   - Evaluation metrics:  
     - Silhouette Score  
     - Davies–Bouldin Index  
     - Calinski–Harabasz Score  
5. **Cluster Profiling**  
   - Exported profiles for each clustering method  
   - Compared behavior across clusters  

---

## 🤖 Models Used
| Model | Train Silhouette | Test Silhouette | Best After Tuning | Observations |
|--------|------------------|-----------------|------------------|---------------|
| **KMeans** | 0.3627 | 0.4056 | 0.4280 | ✅ Stable, generalizes well |
| **GMM** | 0.4224 | 0.3257 | 0.4285 | ⚠ Slight overfitting |
| **Agglomerative** | 0.7229 | — | 0.7355 | ⚠ Overfitted to training data |
| **DBSCAN** | 0.5161 | — | 0.5506 | ⚠ Sensitive to parameters |

---

## 🧠 Model Recommendation
### ✅ **Best Model: KMeans**
**Reasons:**
- Stable performance across train/test sets  
- Tuned Silhouette Score: **0.4280**  
- Predicts clusters for new customers easily  
- Simple, interpretable, and scalable  

**Business Value:**
- Enables targeted campaigns for high-value clusters  
- Improves conversion rates for membership cards  
- Supports continuous segmentation for new data  

---

## 📈 Results & Visuals
All figures are available under:
```
files/images/
```
Key visuals include:
- `corr_heatmap.png` – Correlation between features  
- `eda_01.png` to `eda_03.png` – Data distributions  
- `optimal_k_sil.png` – KMeans optimal cluster visualization  
- `model_comparision.png` – Performance comparison  
- `cluster_before_tuning.png`, `cluster_after_tuning.png` – Cluster evolution  

Cluster profiles and performance summaries are saved under:
```
files/cluster_profiles/
```

---

## 🧩 Models and Artifacts
All trained models and scaler are stored in:
```
models/
```
| File | Description |
|------|--------------|
| `KMeans_model.pkl` | Final chosen model |
| `GMM_model.pkl` | Gaussian Mixture model |
| `Agglomerative_model.pkl` | Hierarchical model |
| `DBSCAN_model.pkl` | Density-based model |
| `scaler.pkl` | StandardScaler object |

---

## 🧪 How to Run the Notebook
1. Open the notebook:
   ```bash
   retrain.ipynb
   ```
2. Run all cells sequentially to:
   - Load and preprocess data  
   - Train clustering models  
   - Compare performance metrics  
   - Save cluster profiles and model outputs  

3. Outputs (images, CSVs, models) will be saved automatically under `/files` and `/models`.

---

## 🗂️ Folder Structure
```
project/
│
├── data/                         # Raw dataset
├── out/                          # Output directory (if any)
│
├── files/
│   ├── cluster_profiles/         # Cluster results and CSVs
│   └── images/                   # Visualizations and evaluation plots
│
├── models/                       # Saved model files (.pkl)
│
├── retrain.ipynb                 # Main Jupyter Notebook
├── README.md                     # Project documentation
└── .gitattributes                # Git config file
```

---

## 🚀 Future Improvements
- Apply dimensionality reduction (PCA) before clustering.  
- Incorporate behavioral features (purchase frequency, category preference).  
- Deploy model as an API for real-time customer segmentation.  

---

## 🧑‍💻 Author
**Name:** [Your Full Name]  
**Date:** November 2025  
**Project:** Machine Learning – Customer Segmentation  

---

**⭐ Final Recommendation:**
> *KMeans clustering provides the best balance of interpretability, stability, and deployability for customer segmentation and membership conversion tasks.*
