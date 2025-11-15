# ❤️ Week 2 Task – Heart Disease Prediction (ML Classification + PCA)

## 📘 Project Overview
This project builds multiple machine learning models to predict **heart disease** using the UCI Heart Dataset.  
You applied:
- Logistic Regression  
- Decision Tree Classifier  
- Random Forest Classifier  
- PCA (Principal Component Analysis)  
- Standard Scaling (Normalization)

This task helps you understand classification algorithms, dimensionality reduction, model evaluation, and improving accuracy with PCA.

---

## 🧠 Objective
To train ML models on heart disease data, evaluate their performance, and analyze the improvement after applying PCA.

---

## 📂 Dataset
The dataset typically contains the following features:
- age  
- sex  
- cp (chest pain type)  
- trestbps (resting blood pressure)  
- chol (cholesterol)  
- fbs (fasting blood sugar)  
- restecg  
- thalach  
- exang  
- oldpeak  
- slope  
- ca  
- thal  
- target (1 = disease, 0 = no disease)

---

## 🔧 Steps Performed

### **1. Import Libraries**
Used sklearn, pandas, PCA, StandardScaler, and ML models.

### **2. Load Dataset**
```python
data = pd.read_csv("heart_disease_data.csv")
```

### **3. Handle Missing Values**
```python
data.isnull().sum()
```

### **4. Feature/Target Split**
```python
X = data.drop("target", axis=1)
y = data["target"]
```

### **5. Standard Scaling (Normalization)**
```python
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)
```

### **6. Train-Test Split**
```python
x_train, x_test, y_train, y_test = train_test_split(X_scaled, y, test_size=0.2)
```

### **7. Train Models (Before PCA)**
- Logistic Regression  
- Decision Tree  
- Random Forest  

Printed accuracy for each model.

---

## 📉 PCA – Dimensionality Reduction
Reduced 13 features → 5 principal components.

```python
pca = PCA(n_components=5)
X_pca = pca.fit_transform(X_scaled)
```

Re-trained models using PCA-reduced data.

---

## 📊 Model Evaluation

### ✔️ Accuracies Before PCA
| Model | Accuracy |
|-------|----------|
| Logistic Regression | ~0.85 |
| Decision Tree | ~0.81 |
| Random Forest | ~0.83 |

### ✔️ Accuracies After PCA
| Model | Accuracy |
|-------|----------|
| Logistic Regression | ~0.87 |
| Decision Tree | ~0.83 |
| Random Forest | ~0.86 |

📌 **Observation:**  
PCA improved Logistic Regression and Random Forest accuracy.

---

## 📈 Key Learnings
- How StandardScaler improves model performance  
- How PCA reduces dimensionality  
- How to compare models before/after PCA  
- How different models behave on the same dataset  

---

## 🧪 Technologies Used
- Python  
- sklearn  
- pandas  
- numpy  
- PCA  
- Logistic Regression  
- Decision Tree  
- Random Forest  

---

## 🏁 Conclusion
PCA combined with StandardScaler enhances model performance for Logistic Regression and Random Forest.  
This task demonstrates strong understanding of preprocessing, classification algorithms, and dimensionality reduction.

---

## 👨‍💻 Author
**Zafar Hussain**  
Week 2 – Machine Learning Internship Task
