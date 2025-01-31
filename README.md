# 🚀 Machine Learning & Deep Learning for Imbalanced Classification

This project tackles a **highly imbalanced binary classification** problem using **Machine Learning (Logistic Regression, Gradient Boosting, XGBoost, Random Forest)** and **Deep Learning (TensorFlow/Keras)**. To address the class imbalance, **sampling techniques** such as **SMOTE, ADASYN, and SMOTETomek** were implemented.

---

## 📂 **Project Overview**
### 1. **Baseline Models:**
   - Logistic Regression & Gradient Boosting
   - Observed high accuracy (~92%) but poor recall for the minority class.
  
### 2. **Deep Learning Approach:**
   - Built a **fully connected neural network**.
   - Achieved high overall accuracy but **failed to correctly classify the minority class (Yes)**.

### 3. **Imbalance Handling:**
   - **SMOTE (Synthetic Minority Oversampling Technique)**
   - **ADASYN (Adaptive Synthetic Sampling)**
   - **SMOTETomek (Combination of SMOTE & Tomek Links)**
   - **Class Weight Adjustment**
   - Applied these techniques and evaluated their impact on deep learning performance.

---

## 📊 **Results Summary**
### 🔹 Logistic Regression & Gradient Boosting
| Model                | Accuracy | ROC AUC  |
|----------------------|----------|----------|
| Gradient Boosting   | 92.70%   | 0.78     |
| Logistic Regression | 92.75%   | 0.76     |

#### 🔍 Key Observations:
- Both models showed **high accuracy (~92%)** but struggled with recall for the minority class.
- The **ROC AUC score suggests poor discriminatory power** for positive cases.

---

### 🔹 Deep Learning Results (Before Addressing Imbalance)
| Metric                | Class 0 (No) | Class 1 (Yes) |
|----------------------|------------|------------|
| **Precision**       | 0.9328     | 0.4749     |
| **Recall**         | 0.9882     | 0.1304     |
| **F1-Score**       | 0.96       | 0.20       |
| **Overall Accuracy** | **92.33%** |

#### 🔍 Key Observations:
- **Severely low recall (13.04%) for Class 1 (Yes).**
- The model is biased toward **majority class (No).**

---

### 🔹 Deep Learning After Handling Class Imbalance
| Method                  | Accuracy | Precision (No) | Recall (No) | Precision (Yes) | Recall (Yes) |
|-------------------------|----------|---------------|------------|----------------|------------|
| **Baseline (No Resampling)**  | 92.33%   | 0.93          | 0.99        | 0.47           | 0.13        |
| **SMOTE**               | 91.85%   | 0.91          | 0.95        | 0.51           | 0.52        |
| **ADASYN**              | 91.12%   | 0.89          | 0.93        | 0.50           | 0.56        |
| **Hybrid (SMOTE+Tomek)**| 92.01%   | 0.92          | 0.96        | 0.52           | 0.49        |
| **Class Weight Adj.**   | 91.45%   | 0.90          | 0.97        | 0.48           | 0.41        |

#### 🔍 Key Observations:
✅ **SMOTE & ADASYN significantly improved recall** for the minority class.  
✅ **ADASYN provided the best recall for Class 1 (Yes) at 56%**.  
✅ **SMOTE + Tomek Links performed well with a balance between precision and recall**.  
✅ **Class Weight Adjustment improved recall but not as much as SMOTE-based methods**.  

---

## 🛠️ **Next Steps**
🔹 **Further Improvements:**  
- Tune **neural network hyperparameters** using **Optuna** or **Talos**.  
- Try **XGBoost with cost-sensitive learning**.  
- Explore **AutoML tools (e.g., AutoKeras, H2O.ai)**.  

🔹 **Deploying the Model:**  
- Convert the best deep learning model into a **REST API using Flask/FastAPI**.  
- Deploy to **AWS/GCP/Azure** for production use.  

---

## 📝 **How to Run the Project**
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/classification-project.git
   cd classification-project
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Run the notebook or script:
   ```bash
   python train_model.py
   ```

---

## 🤝 **Contributions**
Contributions are welcome! If you have ideas for improving the model, feel free to submit a pull request. 🚀  

---

## 🌆 **Tags**
`Machine Learning` `Deep Learning` `Imbalanced Data` `SMOTE` `ADASYN` `XGBoost` `TensorFlow`

