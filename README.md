# 👋 Hi, I'm Xi Ru

## 👩‍💻 About Me

I'm a **Data Scientist** passionate about using data to drive **product decisions, growth, and user experience**. I build **end-to-end analytics and ML solutions** — from experimentation and causal analysis to predictive modeling and deployment — with a focus on measurable business impact and stakeholder-ready insights.

📍 Location: Bellevue, Washington

This repository showcases selected projects built with **real-world datasets**, production-ready code, and reproducible workflows — designed to mirror the work of a data scientist across industries.

---

## 🔍 Focus

* Experimentation & A/B Testing
* Product Analytics, Metrics & Causal Inference
* User Behavior, Retention & Growth Modeling
* End-to-End ML Systems (data → model → deployment)

---

## 🛠️ Skills & Tools

* **Languages:** Python, SQL, R
* **Experimentation:** A/B testing, causal inference, Bayesian methods, power analysis
* **ML / DL:** Scikit-learn, XGBoost, LightGBM, PyTorch, TensorFlow, Hugging Face
* **Data:** pandas, NumPy, PySpark, dbt
* **Big Data:** Spark, Databricks, Delta Lake
* **MLOps & Deployment:** MLflow, Docker, FastAPI, Streamlit, AWS (S3, SageMaker), GitHub Actions
* **Visualization:** Matplotlib, Seaborn, Plotly, Tableau, Power BI

---

## 📂 Featured Projects

Projects are ordered to highlight the skills most relevant to **Product Data Scientist** roles: experimentation, user behavior modeling, and product-impacting ML.

### 🧪 1. A/B Test Analysis — E-commerce Conversion
**Tech:** Python · SciPy · PyMC · Plotly

* Statistical analysis of a randomized experiment using **frequentist and Bayesian** approaches
* Included **power analysis, sample-size calculation, and Simpson's paradox** demonstration
* Delivered a reusable experimentation framework and **stakeholder decision memo**
* **Dataset:** [E-commerce A/B Test (Kaggle)](https://www.kaggle.com/datasets/zhangluyuan/ab-testing)

👉 Repo: [`ab-test-analysis`]([https://github.com/janeruxi1/ab-testing-project])

### 📉 2. Customer Churn Prediction & Retention Analysis
**Tech:** Python · Scikit-learn · XGBoost · SHAP · Streamlit · Docker

* End-to-end churn prediction pipeline with cohort analysis and **driver identification**
* Used **SHAP explainability** to surface actionable retention levers for product teams
* Achieved **ROC-AUC 0.86**, deployed as a Streamlit demo for stakeholder exploration
* **Dataset:** [Telco Customer Churn (IBM / Kaggle)](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

👉 Repo: [`customer-churn-prediction`](./02-customer-churn-prediction)

### 🎬 3. Recommender System — MovieLens
**Tech:** PySpark · implicit · PyTorch · MLflow

* Built collaborative filtering (ALS), content-based, and **hybrid neural recommender (Two-Tower)** models to drive engagement
* Offline evaluation with **NDCG, Recall@K, and uplift simulation** for product impact
* Cold-start handling, scalable PySpark pipeline
* **Dataset:** [MovieLens 25M](https://grouplens.org/datasets/movielens/)

👉 Repo: [`recommender-system`](./03-recommender-system)

### 🧠 4. NLP — Voice of Customer (Review Analysis)
**Tech:** Hugging Face Transformers · PyTorch · BERTopic · FastAPI

* Fine-tuned **DistilBERT** on Amazon reviews for sentiment classification
* Applied **BERTopic** for unsupervised topic discovery to surface product pain points
* Achieved **F1 0.91**, served via FastAPI with a topic-trend dashboard for PM teams
* **Dataset:** [Amazon Product Reviews](https://nijianmo.github.io/amazon/index.html)

👉 Repo: [`nlp-review-analysis`](./04-nlp-review-analysis)

### 📈 5. Retail Demand Forecasting
**Tech:** Python · Prophet · Statsmodels · LightGBM · Power BI

* Hierarchical time-series forecasting for retail SKUs using Prophet, ARIMA, and LightGBM with lag features
* Built a **backtesting framework** and Power BI dashboard
* Benchmarked with WRMSSE, automated retraining pipeline
* **Dataset:** [M5 Forecasting (Walmart)](https://www.kaggle.com/competitions/m5-forecasting-accuracy)

👉 Repo: [`retail-demand-forecasting`](./05-retail-demand-forecasting)

### 💳 6. Credit Risk Scoring & Default Prediction
**Tech:** Python · LightGBM · imbalanced-learn · Fairlearn · MLflow

* Built a credit scoring model on Lending Club data with imbalanced-class handling (SMOTE) and calibration
* Conducted **fairness analysis** across demographic groups
* Achieved **KS statistic 0.42**, tracked experiments with MLflow
* **Dataset:** [Lending Club Loan Data](https://www.kaggle.com/datasets/wordsforthewise/lending-club)

👉 Repo: [`credit-risk-scoring`](./06-credit-risk-scoring)

---

## 🗂️ Repository Structure

Each project follows a consistent, production-style layout:

```
project-name/
├── README.md              # Problem, approach, results
├── data/                  # Raw & processed data (or download script)
├── notebooks/             # EDA and prototyping
├── src/                   # Production code (modular, tested)
│   ├── data/
│   ├── features/
│   ├── models/
│   └── evaluation/
├── tests/                 # Unit tests (pytest)
├── app/                   # Streamlit / FastAPI demo
├── requirements.txt
├── Dockerfile
└── .github/workflows/     # CI pipeline
```

---

## 💡 Skills Demonstrated

* **Experimentation:** A/B test design, power analysis, frequentist & Bayesian inference, causal reasoning
* **Product analytics:** retention, engagement, funnel & cohort analysis, North Star metric definition
* **Problem framing:** translating product questions into measurable, decision-ready analyses
* **Modeling:** classical ML, deep learning, time series, recommender systems, NLP
* **Evaluation:** beyond accuracy — calibration, fairness, business KPIs, uplift
* **Communication:** dashboards, decision memos, stakeholder-friendly visualizations
* **Engineering:** modular code, tests, CI/CD, containerization, deployment

---

## 🚀 How to Run a Project

```bash
git clone https://github.com/janeruxi1/data-science-portfolio.git
cd data-science-portfolio/01-ab-test-analysis
pip install -r requirements.txt
python src/analyze.py
streamlit run app/app.py
```

---

## 🌱 Currently Learning

Generative AI & LLM applications · LLM evaluation & prompt design · Causal inference (DoWhy, EconML) · Quasi-experiments · Real-time ML systems

---

## 📫 Contact

* [LinkedIn](https://www.linkedin.com/in/xiru)
* [GitHub](https://github.com/janeruxi1)
* [Portfolio Website](https://xiru.github.io)
* [Email](mailto:ruthruxi@gmail.com)

⭐ If you find these projects useful, feel free to star the repos or reach out — I'm always open to feedback, collaboration, and **Data Scientist interview conversations**.
