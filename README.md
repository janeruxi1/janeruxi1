# 👋 Hi, I'm Xi Ru
**Product Data Scientist** turning experiments and analytics into product decisions.
*  📍 Redmond, Washington  *  💼 Open to Product Data Scientist roles  *  📫 [ruthruxi@gmail.com](mailto:ruthruxi@gmail.com)

---

## 💡 What I do
I build the data layer that drives product decisions — from experimentation design and stakeholder-ready memos to predictive modeling and deployment. My focus: turn statistics into recommendations a PM, eng lead, or executive can act on without a stats degree.

---

## 🌟 Flagship Projects

Together these two cover the twin questions every subscription business asks: **who to acquire, and how to keep them.** Both are built on synthetic datasets patterned after real subscription-economy dynamics (churn bands, tenure spikes, engagement cohorts, intervention menus) — chosen because designing the data lets me embed known ground truth for validation.

### 🧪 A/B Test Analysis — StreamFlix Trial-to-Paid Experiment
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ab-testing-project.streamlit.app/)
[![CI](https://github.com/janeruxi1/ab-testing-project/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ab-testing-project/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-55%20passing-brightgreen)](https://github.com/janeruxi1/ab-testing-project/tree/main/tests)

End-to-end analysis of a homepage experiment — from PM brief to a ship/don't-ship decision on a 100k-user, 14-column dataset.
- **Experiment design** — pre-registered metric framework (primary / secondary / guardrails), MDE negotiation, power analysis
- **Data quality** — SRM check, covariate balance, sensitivity analysis around an engineered assignment bug
- **Inference** — two-proportion z-test, Welch's t, Holm-Bonferroni correction, Beta-Binomial Bayesian posterior with ROPE
- **Segmentation** — heterogeneous treatment effects across device / country / source / tenure, CUPED variance reduction, Simpson's-paradox check
- **Stakeholder output** — decision memo with hero figure, plain-language verdicts, recommended rollout plan
- **Engineering rigor** — modular `src/` library covered by 55 pytest tests + GitHub Actions CI across Python 3.10/3.11/3.12
- **Interactive demo** — deployed Streamlit app for live sample-size design and A/B analysis

🎮 **[Try the live demo →](https://janeruxi1-ab-testing-project.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/ab-testing-project)**

### 💸 Cost-Aware Churn Retention — StreamFlix Subscriber Targeting
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-churn-retention.streamlit.app/)
[![CI](https://github.com/janeruxi1/StreamFlix-churn-retention/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/StreamFlix-churn-retention/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-61%20passing-brightgreen)](https://github.com/janeruxi1/StreamFlix-churn-retention/tree/main/tests)

An end-to-end retention system that turns a calibrated churn model into a per-user targeting policy under a budget cap. 50k-subscriber dataset with embedded intervention uplifts and per-tier LTV.
- **Data audit + survival analysis** — schema checks, Kaplan-Meier curves, landmark analysis for time-varying covariates
- **Feature engineering** — reusable, idempotent transforms across 5 groups (engagement trend, tenure bucket, recency ratios, lifecycle risk, composite scores)
- **Modeling** — LR baseline → XGBoost with Platt calibration; PR-AUC, Brier, and calibration curve as first-class metrics
- **Experiment tracking** — every model run logged to MLflow (params, metrics, model artifact) so runs are comparable in the UI and reproducible from their tracked params
- **Explainability** — SHAP-driven retention levers tied to actionable interventions (curated playlist $1 / credit $5 / upgrade $12)
- **Decision rule** — expected-value math per user × lever, budget-capped allocation, guardrails for premium offers
- **Sensitivity & ROI** — recommendation robust across ±50% uplift assumptions; policy compared head-to-head against the current blanket campaign
- **Stakeholder output** — one-page decision memo, hero figure, and a Streamlit app the retention team can use directly
- **Modeled impact** — replaces a $6.3k/month loss with +$3.3k/month at 6% of the current spend (a **$9.6k monthly swing**)
- **Engineering rigor** — modular `src/` library covered by 61 pytest tests + GitHub Actions CI, including regression tests for two bugs caught during development

🎮 **[Try the live demo →](https://janeruxi1-streamflix-churn-retention.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/StreamFlix-churn-retention)**

---

## 🗺️ What's next

| Project | Focus area |
|---|---|
| Recommender System on MovieLens | Ranking, engagement, cold-start |
| NLP — Voice of Customer | Sentiment + topic modeling for PM teams |
| Credit Risk Scoring with Fairness Audit | Calibration + subgroup analysis |

---

## 🛠️ Skills & Tools
- **Languages:** Python · SQL · R
- **Experimentation:** A/B testing · Power analysis · Bayesian inference · CUPED · Causal inference
- **ML:** Scikit-learn · XGBoost · SHAP · calibration methods · survival analysis
- **Data:** pandas · NumPy · dbt · PySpark
- **MLOps & Deployment:** MLflow · Docker · FastAPI · Streamlit · AWS (S3, SageMaker) · GitHub Actions
- **Visualization:** Matplotlib · Seaborn · Plotly · Tableau · Power BI

---

## 🎯 What I care about
- **Decision-ready analysis** — every CI, every effect size, every recommendation translated into language a PM or exec can act on
- **Engineering rigor in DS code** — unit tests, CI, reproducibility — not just notebooks
- **Communication** — a decision memo and one hero figure beat a 40-slide deck
- **Honest uncertainty** — confidence intervals, Bayesian credible intervals, sensitivity analyses — never just a point estimate

---

## 📫 Get in touch
- 💼 [LinkedIn](https://www.linkedin.com/in/xiru)
- 📧 [Email](mailto:ruthruxi@gmail.com)
- 🐙 [GitHub](https://github.com/janeruxi1)

If any of this is relevant to a role, a collaboration, or a conversation about experimentation and retention — I'd be glad to hear from you.
