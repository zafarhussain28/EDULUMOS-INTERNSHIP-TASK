# 🎓 Smart Study Score Predictor – Regression Project

## 📘 Objective
The goal of this project is to analyze how study habits, preparation, and lifestyle factors affect exam performance, and to predict a student's exam score (Performance Index) using regression algorithms.

---

## 📂 Dataset Description
The dataset contains 10,000 student records with the following features:

| Feature | Description |
|----------|-------------|
| **Hours Studied** | Number of study hours per day |
| **Previous Scores** | Student’s previous exam performance |
| **Extracurricular Activities** | Whether the student participates in extracurricular activities (Yes/No) |
| **Sleep Hours** | Average hours of sleep per day |
| **Sample Question Papers Practiced** | Number of sample question papers practiced |
| **Performance Index** | Target variable (final performance score) |

---

## ⚙️ Tools & Libraries Used
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  

---

## 🧩 Steps Performed
1. **Data Loading & Cleaning**  
   - Loaded dataset and checked for missing values  
   - Encoded categorical data (`Extracurricular Activities`) using One-Hot Encoding  

2. **Exploratory Data Analysis (EDA)**  
   - Visualized correlations between study habits and performance  
   - Plotted heatmaps and pairplots  

3. **Model Building**  
   - Split dataset into **80% training** and **20% testing**  
   - Applied **Linear Regression** for prediction  

4. **Model Evaluation**  
   - **Mean Absolute Error (MAE):** 1.61  
   - **Root Mean Squared Error (RMSE):** 2.02  
   - **R² Score:** 0.989  

5. **Prediction Section**  
   - Accepts new student input from the user and predicts their expected Performance Index.

---

## 📊 Model Performance
| Metric | Value |
|--------|--------|
| MAE | 1.61 |
| RMSE | 2.02 |
| R² | 0.989 |

✅ The model explains **98.9%** of the variation in student performance — indicating a very strong predictive capability.

---

## 🧠 Feature Importance (Regression Coefficients)
| Feature | Coefficient | Interpretation |
|----------|--------------|----------------|
| Hours Studied | +2.85 | Major positive impact |
| Previous Scores | +1.02 | Strong positive relation |
| Extracurricular Activities (Yes) | +0.61 | Balanced performance improvement |
| Sleep Hours | +0.48 | Proper rest enhances performance |
| Sample Papers Practiced | +0.19 | Practice improves outcomes slightly |

---

## 🧾 Prediction Example
```
Enter number of hours studied per day: 6
Enter previous exam scores: 80
Enter average sleep hours per day: 7
Enter number of sample papers practiced: 3
Does the student participate in extracurricular activities? (Yes/No): Yes
```
Output:
```
📘 Predicted Performance Index: 72.35
```

---

## 🧠 Learning Outcomes
- Data preprocessing and encoding  
- Regression model building  
- Evaluating model performance  
- Real-time prediction handling  

---

## 🧾 Conclusion
The Smart Study Score Predictor demonstrates how machine learning can model and forecast academic performance effectively.  
The regression model achieved an **R² of 0.989**, proving it to be accurate and efficient for educational data analytics.

---

## 📎 Files in This Repository
| File | Description |
|------|--------------|
| `Smart_Study_Score_Predictor.ipynb` | Jupyter Notebook with full implementation |
| `Performance_Dataset.csv` | Dataset used for training and testing |
| `Smart_Study_Score_Predictor_Report.pdf` | Final project report for submission |
| `README.md` | Project documentation |

---

## 🧰 How to Run
1. Clone this repository:  
   ```bash
   git clone https://github.com/<your-username>/Smart-Study-Score-Predictor.git
   cd Smart-Study-Score-Predictor
   ```
2. Install required libraries:  
   ```bash
   pip install pandas numpy matplotlib seaborn scikit-learn
   ```
3. Run the Jupyter Notebook:  
   ```bash
   jupyter notebook Smart_Study_Score_Predictor.ipynb
   ```
4. Enter student details in the input section to see predictions.

---

## 👨‍💻 Author
**Zafar Hussain**  
Machine Learning Internship – November 2025
