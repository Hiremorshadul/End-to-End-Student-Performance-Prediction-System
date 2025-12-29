# 🎓 End-to-End Student Performance Prediction System

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Flask](https://img.shields.io/badge/Flask-2.0%2B-green)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0%2B-orange)
![Bootstrap](https://img.shields.io/badge/Frontend-HTML%2FCSS-yellow)

## 📌 Project Overview
The **Student Performance Prediction System** is an end-to-end machine learning application designed to understand the influence of various demographic and social factors on student achievement. By analyzing variables such as gender, ethnicity, parental education, and test preparation courses, the model predicts the student's **Math Score** with high precision.

This project demonstrates a full-stack data science workflow: from data ingestion and preprocessing to model training, evaluation, and deployment via a modern Flask web interface.

## 🚀 Key Features
- **Exploratory Data Analysis (EDA)**: In-depth analysis of data distribution and correlations.
- **Automated Data Pipeline**: Robust validation, ingestion, and transformation of raw data.
- **Advanced Preprocessing**: Handling missing values, standard scaling, and one-hot encoding via Scikit-Learn pipelines.
- **Model Selection**: Automated comparison of multiple regressors (Random Forest, XGBoost, CatBoost, etc.) to select the best performer.
- **Modern UI/UX**: A responsive, professionally designed web interface for real-time predictions.
- **Deployment Ready**: Configured for deployment on cloud platforms like AWS Elastic Beanstalk.

## 🛠️ Tech Stack
*   **Backend**: Python, Flask
*   **Machine Learning**: Scikit-Learn, Pandas, Numpy, CatBoost, XGBoost, Dill
*   **Frontend**: HTML5, CSS3 (Custom Design System)
*   **DevOps**: Docker (optional), AWS Elastic Beanstalk ready

## 🏗️ Project Architecture
The system follows a modular architecture designed for maintainability and scalability:

1.  **Data Ingestion**: Reading from source (CSV/DB), splitting into train/test sets.
2.  **Data Transformation**:
    *   **Numerical Features**: Imputation (Median) + Standard Scaling.
    *   **Categorical Features**: Imputation (Mode) + One-Hot Encoding.
3.  **Model Trainer**:
    *   Evaluates models: Linear Regression, Lasso, Ridge, K-Neighbors, Decision Tree, Random Forest, XGBoost, CatBoost, AdaBoost.
    *   Hyperparameter Tuning: Uses `GridSearchCV` (CV=3).
    *   **Final Model**: Selects the model with the highest R2 Score on the test set.
4.  **Prediction Pipeline**:
    *   Prepares new input data using the saved `preprocessor.pkl`.
    *   Generates predictions using the saved `model.pkl`.

## 📂 Project Structure
```bash
├── artifacts/              # Generated models and preprocessors (.pkl files)
├── notebook/               # Jupyter notebooks for EDA and experimentation
├── src/                    # Source code
│   ├── components/         # Core ML modules (Ingestion, Transformation, Trainer)
│   ├── pipeline/           # Execution pipelines (Train, Predict)
│   ├── utils.py            # Utility functions
│   ├── logger.py           # Logging configuration
│   └── exception.py        # Custom exception handling
├── static/                 # CSS and assets
├── templates/              # HTML Templates
├── app.py                  # Flask application entry point
├── requirements.txt        # Dependencies
└── setup.py                # Package setup
```

## 💻 Installation & Usage

### 1. Clone the Repository
```bash
git clone https://github.com/Hiremorshadul/End-to-End-Student-Performance-Prediction-System
cd End-to-End-Student-Performance-Prediction-System
```

### 2. Create a Virtual Environment
```bash
conda create -p venv python=3.8 -y
conda activate venv/
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Run the Application
```bash
python app.py
```
Open your browser and navigate to `http://127.0.0.1:5000/` to access the application.

## 📊 Dataset Details
The model is trained on a dataset containing the following features:
*   **Gender**: Male/Female
*   **Race/Ethnicity**: Group A - E
*   **Parental Level of Education**: High school, some college, degree, etc.
*   **Lunch**: Standard or free/reduced (proxy for socio-economic status)
*   **Test Preparation Course**: None or Completed
*   **Reading Score**: Numerical value
*   **Writing Score**: Numerical value

## 🏁 Results
The model consistently achieves an **R2 Score > 0.85** (depending on the specific split), accurately capturing the relationships between socio-economic factors and academic performance.

## 🤝 Contributing
Contributions are welcome! Please feel free to submit a Pull Request.