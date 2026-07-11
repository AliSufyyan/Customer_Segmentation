# 🛍️ Customer Segmentation

An unsupervised Machine Learning project that segments mall customers into 5 distinct groups based on Annual Income and Spending Score using K-Means clustering — with the Elbow Method to determine the optimal number of clusters.

---

## 📌 Project Overview

A mall wants to understand its customers better to run targeted marketing campaigns. This project uses K-Means clustering to discover natural groupings in customer behavior — with no labels, no target variable, and no accuracy metric.

The result: 5 clearly separated customer segments, each with distinct income and spending characteristics, mapped to actionable business strategies.

---

## 📊 Dataset

**File:** `Mall_Customers.csv`

| Property | Value |
|---|---|
| Total Customers | 200 |
| Features Used | 2 (Annual Income, Spending Score) |
| Missing Values | None |
| Optimal Clusters | 5 |

### Why only Annual Income and Spending Score?

These two features directly capture **purchasing power** and **spending behavior** — the most actionable dimensions for retail marketing. Using two features also enables clean 2D cluster visualization without dimensionality reduction.

---

## 🎯 Cluster Results

| Cluster | Color | Income | Spending | Customer Type | Business Action |
|---|---|---|---|---|---|
| 1 | Green | Low | Low | Careful customers | Budget promotions |
| 2 | Red | High | High | Most valuable | Premium loyalty rewards |
| 3 | Yellow | Low | High | Impulsive buyers | Flash sales |
| 4 | Violet | High | Low | Untapped potential | Targeted premium marketing |
| 5 | Blue | Medium | Medium | Standard customers | General promotions |

**Cluster 2** (High Income, High Spending) = most valuable segment — VIP treatment priority.  
**Cluster 4** (High Income, Low Spending) = biggest opportunity — high purchasing power, currently disengaged.

---

## 🔍 How It Works

```
Raw customer data (200 rows)
         ↓
Select Annual Income + Spending Score
         ↓
Run K-Means for K=1 to K=10, record WCSS each time
         ↓
Plot Elbow Graph → identify K=5 as optimal
         ↓
Train K-Means with K=5 (k-means++ initialization)
         ↓
Assign cluster labels (0-4) to each customer
         ↓
Scatter plot with centroids — visualize 5 segments
```

---

## 📈 Elbow Method

WCSS (Within-Cluster Sum of Squares) measures how compact clusters are. Lower = tighter clusters.

Running K-Means from K=1 to K=10 and plotting WCSS shows a sharp drop until K=5, after which improvement flattens — the "elbow point" indicating the optimal cluster count.

---

## 🛠️ Tech Stack

- Python 3.x
- NumPy
- Pandas
- Matplotlib
- Seaborn
- Scikit-learn (KMeans)

---

## 🚀 How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/AliSufyaan/customer-segmentation.git
   cd customer-segmentation
   ```

2. **Install dependencies**
   ```bash
   pip install numpy pandas matplotlib seaborn scikit-learn jupyter
   ```

3. **Run the notebook**
   ```bash
   jupyter notebook Customer_Segmentation.ipynb
   ```

---

## 📁 Project Structure

```
customer-segmentation/
├── Customer_Segmentation.ipynb    # Main notebook
├── Mall_Customers.csv             # Dataset
└── README.md                      # You are here
```

---

## ⚠️ Limitations

- Only 2 of 5 features used — Age and Gender excluded
- K-Means assumes spherical clusters of similar size
- No silhouette score for quantitative cluster quality validation
- Small dataset — 200 customers

---

## 🧠 What I Learned

- K-Means clustering as an unsupervised algorithm — no labels, no accuracy metric
- WCSS as a measure of cluster compactness
- Elbow Method to determine optimal K without labeled guidance
- K-Means++ initialization vs random — why it matters for convergence
- How to translate cluster outputs into real business insights

---

## 📚 Reference

- Dataset: [Kaggle Mall Customer Segmentation](https://www.kaggle.com/datasets/vjchoudhary7/customer-segmentation-tutorial-in-python)
