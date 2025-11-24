# 🛒 Week 2 – Task 3: Customer Segmentation using K-Means

## 📘 Project Overview
In this task, I implemented **Customer Segmentation** using the popular **Mall Customers dataset**.  
The goal is to group customers based on their **Age**, **Annual Income**, and **Spending Score** using **K-Means Clustering**.

This task is part of the Edulumos Machine Learning Internship (Week 2, Task 3 – Customer Universe: Grouping Shoppers with K-Means).

---

## 🧠 Objective
To segment customers into meaningful groups based on their shopping behavior so that businesses can:
- Identify **high-value customers**
- Understand **spending patterns**
- Design better **targeted marketing strategies**

---

## 📂 Dataset Description
The dataset contains **200 customers** with the following columns:

| Column | Description |
|--------|-------------|
| `CustomerID` | Unique ID assigned to each customer |
| `Gender` | Male / Female |
| `Age` | Age of the customer |
| `Annual Income (k$)` | Annual income in thousand dollars |
| `Spending Score (1-100)` | Score assigned based on spending habits and behavior |

---

## 🔧 Steps Performed

### 1️⃣ Import Libraries & Load Data
Loaded the CSV file using **pandas** and checked for:
- Data shape
- Data types
- Missing values

### 2️⃣ Data Preprocessing
- Dropped `CustomerID` (not useful for clustering)
- Encoded `Gender` column:  
  - Male → 0  
  - Female → 1  

### 3️⃣ Feature Selection
Used the key features for clustering:
- `Age`
- `Annual Income (k$)`
- `Spending Score (1-100)`
- (Optionally `Gender` after encoding)

### 4️⃣ Feature Scaling
Applied **StandardScaler** to normalize features so that all variables contribute equally to distance calculation.

```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

### 5️⃣ Choosing Number of Clusters – Elbow Method
Used the **Elbow Method** by plotting **WCSS (Within-Cluster Sum of Squares)** vs **k** (number of clusters).

```python
from sklearn.cluster import KMeans

wcss = []
for k in range(2, 11):
    kmeans = KMeans(n_clusters=k, random_state=42, n_init=10)
    kmeans.fit(X_scaled)
    wcss.append(kmeans.inertia_)
```

The elbow curve suggested an optimal value of **k ≈ 5** clusters.

### 6️⃣ Applying K-Means
```python
kmeans = KMeans(n_clusters=5, random_state=42, n_init=10)
clusters = kmeans.fit_predict(X_scaled)
```

Added the cluster labels back to the original dataset as a new column `Cluster`.

### 7️⃣ Visualization
Plotted clusters using:
- **Annual Income vs Spending Score**
- Different colors to represent clusters

This helps visualize:
- High-income, high-spending customers
- Low-income, low-spending customers
- Moderate groups

---

## 📊 Insights & Interpretation (Example)
Based on the clusters, we can interpret groups like:

- **Cluster 0** → Low income, low spending → Budget-conscious customers  
- **Cluster 1** → High income, high spending → Premium/VIP customers  
- **Cluster 2** → High income, low spending → Potential customers (untapped)  
- **Cluster 3** → Young with high spending → Trend-focused, brand-conscious  
- **Cluster 4** → Moderate income & spending → Average regular customers  

These insights help in **targeted marketing** and **customer relationship strategies**.

---

## 🧪 Technologies Used
- Python  
- pandas, numpy  
- matplotlib, seaborn  
- scikit-learn (StandardScaler, KMeans)  

---

## 🏁 Conclusion
This task demonstrates how **unsupervised learning** can be used to understand customer behavior without labeled outputs.  
K-Means clustering allowed us to group shoppers into meaningful segments which are very useful in real-world business and marketing applications.

---

## 👨‍💻 Author
**Zafar Hussain**  
Edulumos Machine Learning Internship – Week 2, Task 3
