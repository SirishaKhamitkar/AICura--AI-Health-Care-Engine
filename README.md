# AICura - AI-Health-Care-Engine

AICura is an applied machine learning system that delivers **early disease risk prediction**, **health behavior support**, and **personalized healthcare recommendations** through a scalable web-based architecture.

This project emphasizes **end-to-end ML engineering** — from data preprocessing and model selection to evaluation, backend integration, and deployment readiness — within a real-world healthcare context.

---

## 🧠 Core Machine Learning Capabilities

### Disease Risk Prediction (Binary Classification)

The system predicts the likelihood of the following conditions:

- Heart Disease  
- Liver Disease (LPD)  
- Diabetes  

### Models Implemented

- **Support Vector Machine (SVM)**
- **K-Nearest Neighbors (KNN)**

Models are evaluated **per disease**, allowing algorithm selection based on empirical performance rather than assumptions.

---

## 🧪 Machine Learning Pipeline

### 1. Data Ingestion
- Structured clinical and lifestyle parameters
- Disease-specific input schemas

### 2. Data Preprocessing
- Missing value imputation (median / mode)
- Encoding of categorical variables
- Feature normalization for numerical stability

### 3. Feature Selection
- Statistical relevance analysis
- Correlation-based feature filtering to reduce noise

### 4. Model Training
- 80/20 train–test split
- Cross-validation to minimize overfitting
- Disease-wise model tuning

### 5. Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-score
- AUC-ROC

---

## 📊 Model Performance Results

### Heart Disease Prediction

| Model | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|------|---------|-----------|--------|---------|---------|
| SVM  | 0.91 | 0.92 | 0.90 | 0.91 | 0.93 |
| KNN  | 0.88 | 0.87 | 0.86 | 0.86 | 0.89 |

**Insight:**  
SVM demonstrates stronger generalization and class separation for heart disease prediction.

---

### Liver Disease Prediction (LPD)

| Model | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|------|---------|-----------|--------|---------|---------|
| SVM  | 0.83 | 0.82 | 0.81 | 0.81 | 0.84 |
| KNN  | 0.87 | 0.88 | 0.86 | 0.87 | 0.89 |

**Insight:**  
KNN outperforms SVM due to its ability to capture local neighborhood patterns in liver disease data.

---

### Diabetes Prediction

| Model | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|------|---------|-----------|--------|---------|---------|
| SVM  | 0.89 | 0.90 | 0.88 | 0.89 | 0.91 |
| KNN  | 0.85 | 0.84 | 0.83 | 0.83 | 0.86 |

**Insight:**  
SVM achieves superior performance for diabetes risk classification across all evaluation metrics.

> 🔍 **Key Engineering Signal:**  
> Model selection is **data-driven and disease-specific**, not one-size-fits-all.

---

## 📈 Visual Model Evaluation

### ROC Curves
ROC curves illustrate the trade-off between True Positive Rate and False Positive Rate.  
Higher AUC values indicate stronger class separation and robustness.



### Confusion Matrices
Confusion matrices provide insight into false positives and false negatives, which is critical in healthcare-related ML systems.

---

## 🏗 System Architecture (Production-Oriented)

|Client (Browser)|
↓
|Django Backend (Routing, Auth, Business Logic)|
↓
|ML Inference Layer (SVM / KNN)|
↓
|Persistence Layer (SQLite)|
↓
|Notification & Scheduling Engine|


### Architecture Highlights
- ML inference isolated from request-handling logic
- Modular design enabling REST / microservice expansion
- Clear separation between preprocessing, inference, and storage
- Designed for cloud deployment and scalability

---

## 🥗 Intelligent Recommendation Systems

### Diet Recommendation Engine
- Condition-aware food classification
- Evaluates food suitability per disease category
- Supports risk reduction through informed decisions

### Medication Adherence System
- User-defined medication schedules
- Reminder-based intervention
- Demonstrates applied AI beyond prediction (behavioral impact)

---

## 🛠 Technology Stack

| Layer | Technology |
|-----|-----------|
| Language | Python |
| Machine Learning | Scikit-learn |
| Backend | Django |
| Database | SQLite |
| Frontend | HTML, CSS, JavaScript |
| Version Control | Git |
| ML Paradigm | Supervised Learning (Classification) |

---

## 🚀 Running the Project Locally

```bash
git clone https://github.com/your-username/aicura.git
cd aicura
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver
Access the application at:

http://127.0.0.1:8000/
