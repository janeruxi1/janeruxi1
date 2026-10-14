# 👋 Hi, I'm Xi Ru
**Data Scientist** turning experiments, models, and analytics into decisions a business can act on.

📍 Redmond, Washington<br>
💼 Open to Data Scientist roles — product, decision science, applied ML, analytics<br>
📫 [ruthruxi@gmail.com](mailto:ruthruxi@gmail.com)

---

## 💡 What I do
I work on the question behind the analysis: what should we do, and how sure are we? That covers experiment design and causal inference, predictive modeling and forecasting, pricing and constrained optimization, cost-aware decision rules, and evaluating LLM systems — each one finished as a recommendation that a product, operations, finance, or engineering lead can act on without a stats degree.

---

## 🌟 Flagship Projects

### 🚕 Driver Pay Pricing — NYC Ride-Hailing Marketplace (real data)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/)
[![CI](https://github.com/janeruxi1/ridehail-driver-pay-optimization/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ridehail-driver-pay-optimization/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-29%20passing-brightgreen)](https://github.com/janeruxi1/ridehail-driver-pay-optimization/tree/main/tests)

What should a ride-hailing platform offer a driver for each trip? Pay too little and riders wait and drivers decline; pay too much and the margin disappears. Built end to end on **360 million real trips** from New York City's Taxi & Limousine Commission records (January 2024 – June 2025); driver accept/decline decisions, which the public data doesn't record, are simulated with a known truth so every causal method can be checked.
- **Spark pipeline at scale** — PySpark processes 18 monthly files one at a time into compact tables; every cleaning rule is counted per month (99.88% of trips kept), and two rules were corrected after the first real month showed they removed real trips; marketplace health built in DuckDB SQL from sums, not averages of averages
- **Pay is the legal floor plus a premium** — the median trip is paid 1.003× New York's minimum pay; the premium above it (7.9% of driver pay) is the lever priced; zones grouped by k-means chosen for stability under bootstrap resampling
- **Forecasting and classification** — four-week demand forecast by zone and hour (LightGBM, rolling-origin backtest, 12.7% weighted error against a 6.8% Poisson noise floor); a calibrated long-wait classifier with a cost-based threshold fixed before testing
- **A real natural experiment** — the 2025 Manhattan congestion fee made traffic in the zone 4.6% faster, robust to placebo dates; clustered standard errors called 82% of fake start dates "significant", so every effect is judged against the placebo distribution and the effect on driver pay is reported as not measurable
- **Causal effect of pay** — the raw history credits pay with half its true effect, because premiums go to the trips drivers dislike; double machine learning and a randomized pay test each recover their estimand, a hidden-confounder scenario shows why the randomized slice is kept, and a Bayesian hierarchical model (PyMC) gives curves by segment
- **Constrained optimization** — a mixed-integer program sets premiums under rider-wait, acceptance and driver-earnings guardrails that must hold in 20 posterior draws at once: **+2.8% margin** on held-out months with every guardrail met, where paying only the minimum looks like +27% and breaks all three
- **Simulation and rollout** — a discrete-event dispatch simulation replays real Brooklyn requests with driver supply calibrated hour by hour to real waits (batched Hungarian matching vs greedy); a switchback test sized on real block-to-block variation with randomization inference
- **Production** — FastAPI quote service in Docker (~1 ms per quote, versioned model artifact, model card), GitHub Actions CI that runs every notebook on a synthetic city, and CD publishing the image on merge

🎮 **[Try the live demo →](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/ridehail-driver-pay-optimization)**

### 🏨 Hotel Search Ranking — Expedia Search Logs (real data)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-hotel-search-ranking.streamlit.app/)
[![CI](https://github.com/janeruxi1/Hotel-Search-Ranking/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/Hotel-Search-Ranking/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-69%20passing-brightgreen)](https://github.com/janeruxi1/Hotel-Search-Ranking/tree/main/tests)

A ranking team wants to push cheaper hotels up the search results. Before they spend an A/B test slot on it: how much does position matter, what drives the choice, and which ranking should be tested? Built on Expedia's ICDM 2013 release (9.9M impressions, 399k searches), 30% of which were shown in random order.
- **Causal effect from logs** — the randomly ordered searches show the naive reading of ranked traffic overstates position effects **3.4×** (95% CI 3.2–3.7); a balanced panel removes a composition bias that inflated the first estimate, and the click slope matches a published study on the same data
- **Discrete choice model** — a conditional logit written from scratch (Newton's method, analytic Hessian), with a within-hotel price effect that is more than twice the naive one; moving from position 10 to 1 is worth a **$56** price cut for clicks
- **Pre-declared decision rule** — committed to git before the evaluation ran; four rankings scored offline on held-out searches with bootstrap and coefficient-draw intervals. Cheapest first loses on both bookings and booking value (−24%)
- **Honest about the limits** — cross-fitting shows the evaluator does not flatter its own rankings, but a direct check of the mechanism behind the offline gains is inconclusive, so the memo recommends a test rather than a launch; a bias found in that check during review was fixed and documented
- **Experiment design** — a three-arm test sized with power analysis, verified by simulation, where the 2% booking-value guardrail, not the booking lift, sets the size (616k searches per arm), turning a statistical detail into a business decision
- **Stakeholder output** — decision memo, executed notebook per phase ending in a written verdict, and a live demo with a test-sizing calculator
- **SQL data preparation** — the audit's search-level tables, data-quality flags and analysis sample are built in DuckDB SQL on all 9.9M rows (window functions for a within-search rank correlation, `LAG`/`LEAD` slot checks), each query tested against an independent pandas implementation
- **Engineering rigor** — 69 pytest tests + GitHub Actions CI on a synthetic stand-in (the data may not be redistributed); memo and README numbers verified against the measured records on every push

🎮 **[Try the live demo →](https://janeruxi1-hotel-search-ranking.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/Hotel-Search-Ranking)**

### 🧪 A/B Test Analysis — StreamFlix Trial-to-Paid Experiment
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ab-testing-project.streamlit.app/)
[![CI](https://github.com/janeruxi1/StreamFlix-AB-Testing/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/StreamFlix-AB-Testing/actions)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-62%20passing-brightgreen)](https://github.com/janeruxi1/StreamFlix-AB-Testing/tree/main/tests)

End-to-end analysis of a homepage experiment — from PM brief to a ship/don't-ship decision on a synthetic 100k-user, 14-column dataset.
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

An end-to-end retention system that turns a calibrated churn model into a per-user targeting policy under a budget cap. Synthetic 50k-subscriber dataset with embedded intervention uplifts and per-tier LTV.
- **Data audit + survival analysis** — schema checks, Kaplan-Meier curves, landmark analysis for time-varying covariates
- **Feature engineering** — reusable, idempotent transforms across 5 groups (engagement trend, tenure bucket, recency ratios, lifecycle risk, composite scores)
- **Modeling** — LR baseline → calibrated HistGradientBoosting, chosen in a bake-off across 4 model families with Optuna tuning; PR-AUC, Brier, and calibration curve as first-class metrics
- **Experiment tracking** — every model run logged to MLflow (params, metrics, model artifact) so runs are comparable in the UI and reproducible from their tracked params
- **Explainability** — SHAP-driven retention levers tied to actionable interventions (curated playlist \$1 / credit \$5 / upgrade \$12)
- **Decision rule** — expected-value math per user × lever, budget-capped allocation, guardrails for premium offers
- **Causal uplift** — S/T/X-learners with Qini and decile-lift evaluation, checked against the simulator's ground truth
- **Sensitivity & ROI** — sensitivity analysis on budget and intervention cost; policy compared head-to-head against the current blanket campaign
- **Stakeholder output** — one-page decision memo, hero figure, and a Streamlit app the retention team can use directly
- **Modeled impact** — replaces a \$4.8k/month loss with +\$19.1k net expected value at 1.64× ROI (a **\$23.9k monthly swing**)
- **Engineering rigor** — modular `src/` library covered by 88 pytest tests + GitHub Actions CI, including regression tests for two bugs caught during development

🎮 **[Try the live demo →](https://janeruxi1-streamflix-churn-retention.streamlit.app/)**
👉 **[Browse the code →](https://github.com/janeruxi1/StreamFlix-Churn-Retention)**

### 🔎 RAG Evaluation — StreamFlix Support Assistant
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/)
[![CI](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](https://www.python.org/)
[![Tests](https://img.shields.io/badge/tests-511%20passing-brightgreen)](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/tree/main/tests)

An evaluation harness for a retrieval-augmented support assistant over a synthetic 45-article help centre written for the fictional StreamFlix service. The deliverable is not the assistant but a deployment memo, with every number in it checked by CI.
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

## 🛠️ Skills & Tools
- **Languages:** Python · SQL · R
- **Experimentation & causal inference:** A/B testing · Power analysis · Switchback tests · Bayesian inference · CUPED · Uplift modeling · Difference-in-differences · Double machine learning
- **Decision science & optimization:** Expected-value modeling · Budget-constrained allocation · Constrained optimization (mixed-integer programming) · Discrete-event simulation · Pre-declared decision rules · Offline policy evaluation · Sensitivity analysis
- **Statistics & econometrics:** Discrete choice (conditional logit) · Fixed effects · Bayesian hierarchical models (PyMC) · Delta method · Bootstrap inference
- **ML:** Scikit-learn · XGBoost · LightGBM · Time-series forecasting · Clustering · SHAP · calibration methods · survival analysis
- **LLM & retrieval:** RAG evaluation · LLM-as-judge validation · BM25 · sentence-transformers · OpenAI API
- **Data & databases:** pandas · NumPy · PySpark · DuckDB · Databricks · SQL Server · Oracle (SQL Developer)
- **Apps & MLOps:** Streamlit · FastAPI · Docker · Flask · MLflow · GitHub Actions CI/CD
- **Visualization & BI:** Matplotlib · Seaborn · Plotly · Power BI · Tableau
- **Tools:** RStudio · Jupyter · Git

*Databricks, SQL Server, Oracle, Power BI, Tableau, R and Flask come from my day-to-day work, so they don’t appear in these repositories.*

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

If any of this is relevant to a role, a collaboration, or a conversation about experimentation, decision science, pricing, retention, or LLM evaluation — I'd be glad to hear from you.
