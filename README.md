# 👋 Hi, I'm Xi Ru
**Data Scientist** turning experiments, models, and analytics into decisions a business can act on.
*  📍 Redmond, Washington  *  💼 Open to Data Scientist roles — product, decision science, applied ML, analytics  *  📫 [ruthruxi@gmail.com](mailto:ruthruxi@gmail.com)

---

## 💡 What I do
I work on the question behind the analysis: what should we do, and how sure are we? That covers experiment design and causal inference, predictive modeling, cost-aware decision rules, and evaluating LLM systems — each one finished as a recommendation that a product, operations, finance, or engineering lead can act on without a stats degree.

---

## 🌟 Flagship Projects

The first two cover the twin questions every subscription business asks: **who to acquire, and how to keep them.** The third asks a newer one: **is an AI support assistant safe to put in front of customers, and how would we know?** All three share the same fictional streaming service, StreamFlix, and are built on synthetic data — chosen because designing the data lets me embed known ground truth for validation.

| If the role is about… | Start with |
|---|---|
| Experimentation and causal inference | A/B test analysis; the uplift models in the churn project |
| Decisions under cost and budget constraints | Churn: expected-value targeting under a budget cap. RAG: break-even model and pilot sizing |
| Predictive modeling and ML | Churn: calibrated model, four-family bake-off, MLflow tracking |
| LLM and AI evaluation | RAG evaluation harness |
| Product analytics and metrics | A/B test: metric framework, guardrails, segmentation |

### 🧪 A/B Test Analysis — StreamFlix Trial-to-Paid Experiment
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ab-testing-project.streamlit.app/)
[![CI](https://github.com/janeruxi1/StreamFlix-AB-Testing/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/StreamFlix-AB-Testing/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-62%20passing-brightgreen)](https://github.com/janeruxi1/StreamFlix-AB-Testing/tree/main/tests)

End-to-end analysis of a homepage experiment — from PM brief to a ship/don't-ship decision on a 100k-user, 14-column dataset.
- **Experiment design** — pre-registered metric framework (primary / secondary / guardrails), MDE negotiation, power analysis
- **Data quality** — SRM check, covariate balance, sensitivity analysis around an engineered assignment bug
- **Inference** — two-proportion z-test, Welch's t, Holm-Bonferroni correction, Beta-Binomial Bayesian posterior with ROPE
- **Segmentation** — heterogeneous treatment effects across device / country / source / tenure, CUPED variance reduction, Simpson's-paradox check
- **Validation against known truth** — the simulator's true effect (+2.29pp) sits inside the estimate's interval, and a 300-run simulation gives 95.3% interval coverage
- **Stakeholder output** — decision memo with hero figure, plain-language verdicts, recommended rollout plan
- **Engineering rigor** — modular `src/` library covered by 62 pytest tests + GitHub Actions CI across Python 3.10/3.11/3.12
- **Interactive demo** — deployed Streamlit app for live sample-size design and A/B analysis

🎮 **[Try the live demo →](https://janeruxi1-ab-testing-project.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/StreamFlix-AB-Testing)**

### 💸 Cost-Aware Churn Retention — StreamFlix Subscriber Targeting
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-churn-retention.streamlit.app/)
[![CI](https://github.com/janeruxi1/StreamFlix-Churn-Retention/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/StreamFlix-Churn-Retention/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-88%20passing-brightgreen)](https://github.com/janeruxi1/StreamFlix-Churn-Retention/tree/main/tests)

An end-to-end retention system that turns a calibrated churn model into a per-user targeting policy under a budget cap. 50k-subscriber dataset with embedded intervention uplifts and per-tier LTV.
- **Data audit + survival analysis** — schema checks, Kaplan-Meier curves, landmark analysis for time-varying covariates
- **Feature engineering** — reusable, idempotent transforms across 5 groups (engagement trend, tenure bucket, recency ratios, lifecycle risk, composite scores)
- **Modeling** — LR baseline → calibrated HistGradientBoosting, chosen in a bake-off across 4 model families with Optuna tuning; PR-AUC, Brier, and calibration curve as first-class metrics
- **Experiment tracking** — every model run logged to MLflow (params, metrics, model artifact) so runs are comparable in the UI and reproducible from their tracked params
- **Explainability** — SHAP-driven retention levers tied to actionable interventions (curated playlist $1 / credit $5 / upgrade $12)
- **Decision rule** — expected-value math per user × lever, budget-capped allocation, guardrails for premium offers
- **Causal uplift** — S/T/X-learners with Qini and decile-lift evaluation, checked against the simulator's ground truth
- **Sensitivity & ROI** — sensitivity analysis on budget and intervention cost; policy compared head-to-head against the current blanket campaign
- **Stakeholder output** — one-page decision memo, hero figure, and a Streamlit app the retention team can use directly
- **Modeled impact** — replaces a $4.8k/month loss with +$19.1k net expected value at 1.64× ROI (a **$23.9k monthly swing**)
- **Engineering rigor** — modular `src/` library covered by 88 pytest tests + GitHub Actions CI, including regression tests for two bugs caught during development

🎮 **[Try the live demo →](https://janeruxi1-streamflix-churn-retention.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/StreamFlix-Churn-Retention)**

### 🔎 RAG Evaluation — StreamFlix Support Assistant
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/)
[![CI](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-511%20passing-brightgreen)](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/tree/main/tests)

An evaluation harness for a retrieval-augmented support assistant over a 45-article help centre. The deliverable is not the assistant but a deployment memo, with every number in it checked by CI.
- **Golden set written first** — 120 questions with hand-labelled sources, written before any retrieval code, including 25 the help centre deliberately *cannot* answer so refusal is measured rather than assumed
- **Retrieval bake-off** — 64 configurations compared with paired bootstrap inference, Holm-Bonferroni correction, and held-out selection; BM25 was not beaten by a transformer on the same chunks (+0.025 [-0.039, +0.090])
- **A judge that is tested before it is trusted** — `gpt-4o` passes a 9-case gate at 100% where a lexical judge scores 50%, then gets audited for length and context-order bias
- **Measured, then bounded** — the cited prompt refused 25 of 25 unanswerable questions with zero fabricated citations, and the memo still recommends a pilot because 25 questions only bound the true refusal rate at 86.7%
- **A pre-registered test against no retrieval** — the decision rule was committed before the run; sending the model every article gave the same answers, so the memo leads with "retrieval is optional at this size"
- **Decision model** — with a cost placed on a wrong answer, the bad-answer rate moves the system's value 5.8× as much as the refusal rate, and the pilot is sized to measure it
- **Stakeholder output** — decision memo, pilot design brief, and a live demo that replays every measured answer beside the judge's verdict
- **A corrected mistake, left visible** — building the demo exposed that the refusal check had miscounted the control prompt (0 of 25 refusals reported, 9 on reading); the check is now validated against 88 hand-labelled answers
- **Engineering rigor** — 511 pytest tests + GitHub Actions CI across Python 3.10/3.11/3.12, secret scanning, and 100 figures in the memo and pilot brief verified against the measured records on every push

🎮 **[Try the live demo →](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/StreamFlix-RAG-evaluation)**

---

## 🗺️ What's next

| Project | Focus area |
|---|---|
| Recommender System on MovieLens | Ranking, engagement, cold-start |
| NLP — Voice of Customer | Sentiment + topic modeling for product and support teams |
| Credit Risk Scoring with Fairness Audit | Calibration + subgroup analysis |

---

## 🛠️ Skills & Tools
- **Languages:** Python · SQL · R
- **Experimentation & causal inference:** A/B testing · Power analysis · Bayesian inference · CUPED · Uplift modeling
- **Decision science:** Expected-value modeling · Budget-constrained allocation · Sensitivity analysis · Break-even analysis
- **ML:** Scikit-learn · XGBoost · SHAP · calibration methods · survival analysis
- **LLM & retrieval:** RAG evaluation · LLM-as-judge validation · BM25 · sentence-transformers · OpenAI API
- **Data:** pandas · NumPy · dbt · PySpark
- **MLOps & Deployment:** MLflow · Docker · FastAPI · Streamlit · AWS (S3, SageMaker) · GitHub Actions
- **Visualization:** Matplotlib · Seaborn · Plotly · Tableau · Power BI

---

## 🎯 What I care about
- **Decision-ready analysis** — every CI, every effect size, every recommendation translated into language the person who owns the decision can act on
- **Engineering rigor in DS code** — unit tests, CI, reproducibility — not just notebooks
- **Communication** — a decision memo and one hero figure beat a 40-slide deck
- **Honest uncertainty** — confidence intervals, Bayesian credible intervals, sensitivity analyses — never just a point estimate

---

## 📫 Get in touch
- 💼 [LinkedIn](https://www.linkedin.com/in/xiru)
- 📧 [Email](mailto:ruthruxi@gmail.com)
- 🐙 [GitHub](https://github.com/janeruxi1)

If any of this is relevant to a role, a collaboration, or a conversation about experimentation, decision science, retention, or LLM evaluation — I'd be glad to hear from you.
