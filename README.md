# 🛒 Customer Segmentation Using Clustering

## 📘 Project Overview
This project performs **customer segmentation** for a supermarket chain to improve **membership card conversion rates** using **unsupervised machine learning**.  
By identifying distinct customer groups based on demographics and spending behavior, marketing teams can craft personalized offers and improve engagement.

---

## 🎯 Problem Statement
Supermarkets face challenges in increasing membership card sign-ups because marketing efforts target all customers uniformly.  
The goal is to **segment customers into distinct groups** to enable:
- Personalized marketing  
- Better understanding of customer behavior  
- Improved conversion and retention rates  

---

## 📂 Dataset Information
- **Source:** Provided dataset (`/data`)  
- **Records:** 200 customers  
- **Features:**
  - `Age`
  - `Gender` (encoded)
  - `Annual Income`
  - `Spending Score`

**Preprocessing Steps:**
- Handled missing values  
- Encoded categorical variables  
- Applied feature scaling (`StandardScaler`)  
- Split data into train and test sets  

---

## ⚙️ Workflow Summary
1. **Exploratory Data Analysis (EDA)**  
   - Visualized feature distributions and correlations  
   - Generated heatmaps and pairplots  
2. **Feature Engineering**  
   - Standardized numerical features  
3. **Model Training & Evaluation**  
   - Trained multiple clustering algorithms:
     - KMeans  
     - Gaussian Mixture Model (GMM)  
     - Agglomerative Clustering  
     - DBSCAN  
4. **Model Evaluation Metrics**
   - Silhouette Score  
   - Davies–Bouldin Index  
   - Calinski–Harabasz Score  
5. **Cluster Profiling**
   - Analyzed customer characteristics per cluster  
   - Exported profiles to CSV  

---

## 🤖 Model Comparison

| Model | Train Silhouette | Test Silhouette | After Tuning | Observations |
|--------|------------------|-----------------|---------------|---------------|
| **KMeans** | 0.3627 | 0.4056 | **0.4280** | ✅ Stable and generalizes well |
| **GMM** | 0.4224 | 0.3257 | 0.4285 | ⚠ Slight overfitting |
| **Agglomerative** | 0.7229 | — | 0.7355 | ⚠ Overfitted to training data |
| **DBSCAN** | 0.5161 | — | 0.5506 | ⚠ Sensitive to parameters |

---

## 🧠 Final Model Recommendation — **KMeans**
### Why KMeans?
- Consistent performance on train and test sets  
- Tuned Silhouette Score: **0.4280**  
- Simple, interpretable, and scalable  
- Capable of predicting new customer segments easily  

**Business Impact:**
- Enables targeted marketing for high-value clusters  
- Boosts membership card conversion  
- Supports automated segmentation for future data  

---

## 📊 Key Visuals
Stored in `out/images/`:

| Visualization | Description |
|----------------|--------------|
| `corr_heatmap.png` | Feature correlations |
| `eda_01.png` – `eda_03.png` | Exploratory analysis |
| `optimal_k_sil.png` | Optimal cluster (KMeans) |
| `model_comparision.png` | Model comparison summary |
| `cluster_before_tuning.png`, `cluster_after_tuning.png` | Clustering improvement |

Cluster summaries available in:  
`out/files/cluster_profiles/`

---

## 🧩 Saved Models & Artifacts
Located in `out/models/`:

| File | Description |
|------|--------------|
| `KMeans_model.pkl` | Final selected model |
| `GMM_model.pkl` | Gaussian Mixture Model |
| `Agglomerative_model.pkl` | Hierarchical model |
| `DBSCAN_model.pkl` | Density-based model |
| `scaler.pkl` | Feature scaler |

---

## 🧪 How to Run
1. Open the notebook:
   ```bash
   retrain.ipynb
   ```
2. Execute all cells to:
   - Load and preprocess data  
   - Train and evaluate clustering models  
   - Save outputs (images, CSVs, and models)

Outputs will automatically be saved in `/out/files/` and `/out/models/`.

---

## 🗂️ Project Structure
```
project/
│
├── data/                          # Raw dataset
├── out/
│   ├── files/
│   │   └── cluster_profiles/      # Cluster CSV reports
│   ├── images/                    # Visualizations
│   └── models/                    # Trained models and scaler
│
├── retrain.ipynb                  # Main notebook
├── README.md                      # Project documentation
└── .gitattributes                 # Git configuration
```

---

## 🚀 Future Improvements
- Apply **PCA** for dimensionality reduction before clustering  
- Add behavioral metrics (purchase frequency, product categories)  
- Deploy as an **interactive dashboard or API** for real-time segmentation  

---

## 👤 Author
**Name:** Isula Dissanayake  
**Date:** November 2025  
**Project:** Customer Segmentation using Machine Learning  

---

> **⭐ Final Takeaway:**  
> *KMeans provides the most interpretable, stable, and business-ready segmentation model for optimizing membership marketing strategies.*
