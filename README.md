# 👋 Hi, I'm Xi Ru
**Data Scientist.** I turn experiments, causal analysis, models and forecasts into decisions a business can act on, and I say how sure we are.

📍 Redmond, Washington · 💼 Open to Senior Data Scientist and Data Scientist roles: product, decision science, applied ML, marketplace and pricing · 📫 [ruthruxi@gmail.com](mailto:ruthruxi@gmail.com) · [LinkedIn](https://www.linkedin.com/in/xiru)

---

## ⏱️ The portfolio in one minute

Eight end-to-end projects. Each one starts from a business question and ends with a written recommendation (a decision memo, or a write-up per case for the SQL casebook), and is checked by CI: tests, a rerun of the analysis, and a check that the numbers in the docs match the recorded results.

| Project | The decision | Core methods | Data | Links |
|---|---|---|---|---|
| 🚦 [NYC congestion toll: causal impact](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact) | Should taxi and ride-hail operators offset the new toll? | Difference-in-differences, HonestDiD, forecast counterfactual, synthetic control | **Real**: 1.3B NYC trips | [Demo](https://janeruxi1-nyc-congestion-toll-causal-impact.streamlit.app/) · [Memo](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/blob/main/reports/decision_memo.md) |
| 🚕 [Driver pay pricing](https://github.com/janeruxi1/ridehail-driver-pay-optimization) | What should a ride-hail platform pay a driver per trip? | Double ML, Bayesian hierarchical model, mixed-integer optimization, FastAPI/Docker | **Real**: 360M NYC trips (+ simulated driver choices) | [Demo](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/) · [Memo](https://github.com/janeruxi1/ridehail-driver-pay-optimization/blob/main/reports/decision_memo.md) |
| 💳 [Card fraud decisioning](https://github.com/janeruxi1/card-fraud-decisioning) | Approve, decline or review each payment? | Leakage audit, gradient boosting, calibration, expected-cost policy, drift monitoring | **Real**: 590k payments (IEEE-CIS) | [Demo](https://janeruxi1-card-fraud-decisioning.streamlit.app/) · [Memo](https://github.com/janeruxi1/card-fraud-decisioning/blob/main/reports/decision_memo.md) |
| 🧪 [A/B testing on real experiments](https://github.com/janeruxi1/ab-testing-real-experiments) | Which e-mail to send, and how far to trust a winning test? | Pre-registered readout, SRM, CUPED-style adjustment, Holm, MDE and holdback sizing, empirical-Bayes shrinkage | **Real**: 64k-customer e-mail test; 22,743 Upworthy headline tests | [Demo](https://janeruxi1-ab-testing-project.streamlit.app/) · [Memo](https://github.com/janeruxi1/ab-testing-real-experiments/blob/main/reports/decision_memo.md) |
| 💸 [Churn and retention offers](https://github.com/janeruxi1/churn-uplift-decisioning) | Who will churn, and is a retention offer worth it? | Out-of-time churn model, survival-based lifetime value, propensity-weighted (doubly robust) experiment readout, uplift models | **Real**: 2M KKBox subscriptions; 11,896-customer retention experiment | [Demo](https://janeruxi1-churn-uplift-decisioning.streamlit.app/) · [Memo](https://github.com/janeruxi1/churn-uplift-decisioning/blob/main/reports/decision_memo.md) |
| 🏨 [Hotel search ranking](https://github.com/janeruxi1/Hotel-Search-Ranking) | Which ranking change deserves an A/B test slot? | Causal effect from randomized logs, conditional logit, LambdaMART, A/B test sizing | **Real**: 9.9M Expedia impressions | [Demo](https://janeruxi1-hotel-search-ranking.streamlit.app/) · [Memo](https://github.com/janeruxi1/Hotel-Search-Ranking/blob/main/reports/decision_memo.md) |
| 🧮 [Product analytics in SQL](https://github.com/janeruxi1/ecommerce-sql-product-analytics) | Where does checkout leak, why did revenue fall, did the test win? | BigQuery SQL: funnels, sessionization, cohorts, north-star metric, A/B readout in SQL | GA4 sample (real, obfuscated) + theLook | [Cases](https://github.com/janeruxi1/ecommerce-sql-product-analytics#the-cases) |
| 🔎 [RAG evaluation](https://github.com/janeruxi1/StreamFlix-RAG-evaluation) | Is the LLM support assistant ready for a pilot? | Golden-set design, validated LLM-as-judge, PyTorch fine-tuned ticket router | Synthetic help centre; Banking77 | [Demo](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/) · [Memo](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/blob/main/reports/decision_memo.md) |

**Short on time?** Read the [congestion toll memo](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/blob/main/reports/decision_memo.md) (causal inference on real data), the [driver pay README](https://github.com/janeruxi1/ridehail-driver-pay-optimization) (modeling through to a deployed service), and the [fraud decision table](https://github.com/janeruxi1/card-fraud-decisioning#the-decision) (turning a model score into dollars).

---

## 🧭 What a senior data scientist does, and where to see it

| Responsibility | Where to see it |
|---|---|
| **Frame an ambiguous business question** and agree metrics and guardrails first | Every project opens with a brief and a decision rule; in hotel ranking and RAG evaluation the rule was committed to git before the results existed. |
| **Find the causal effect when there is no experiment** | Congestion toll: three methods that check each other, seven fake toll dates and a HonestDiD sensitivity analysis. Hotel ranking: randomized searches show ranked traffic overstates position effects 3.4×. |
| **Design experiments that answer the decision** | Hotel ranking: a multi-arm test where the guardrail, not the lift, sets the size. Driver pay: a switchback test sized on real variation. A/B testing: an e-mail test sized, checked and rolled out with a holdback. Churn: a "randomized" retention campaign that wasn't, caught by a balance check and read with a doubly robust estimator. |
| **Push back on the easy answer** | Congestion toll: the quick comparison shows −2.6%, but a year with no toll shows −4.4%. The memo says "no detectable effect", not "the toll cut trips". |
| **Turn a model into a decision with a dollar value** | Fraud: the decision layer alone saves $1,070 per 1,000 payments with the same model. Driver pay: a constrained optimizer with guardrails. |
| **Build at production scale and quality** | DuckDB, PySpark and AWS Athena over billions of rows; a FastAPI service in Docker with CD; CI that reruns every notebook and fails if results drift. |
| **Own mistakes in the open** | RAG documents a miscounted refusal check and its fix; hotel ranking documents a position bias found in its own evaluation and corrects it; A/B testing drops a pre-registered question in a dated note when its own check failed. |

---

## 🌟 Featured projects

### 🚦 Did NYC's Congestion Toll Cut Taxi and Uber/Lyft Trips? (real data)
[![CI](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/actions) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-nyc-congestion-toll-causal-impact.streamlit.app/)

- **Answer:** on all 1.3 billion trips from 2022 to August 2026, no detectable effect on trips in year one: **+1.0% (95% CI −0.3% to +2.3%)**. Trips did get 5.0% faster, and shared-ride requests fell 12.7%.
- **Why the quick answer is wrong:** 2025 vs 2024 shows −2.6%, but the same comparison a year earlier, with no toll, shows −4.4%.
- **Stress-tested:** seven fake toll dates, a wild cluster bootstrap, and HonestDiD: a drop of 5% or more stays ruled out unless the zone's decline sped up by more than 131% of its pre-toll pace. The pipeline also runs on AWS S3 + Athena ($0.24, 504 of 504 checks match).

[Demo](https://janeruxi1-nyc-congestion-toll-causal-impact.streamlit.app/) · [Memo](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact)

### 🚕 Driver Pay Pricing: NYC Ride-Hailing Marketplace (real data)
[![CI](https://github.com/janeruxi1/ridehail-driver-pay-optimization/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ridehail-driver-pay-optimization/actions) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/)

- **Result:** a mixed-integer pay policy earns **+3.7% margin per request** on held-out months with rider-wait, acceptance and driver-earnings guardrails met; cutting pay to the legal floor looks like +27% but breaks all three.
- **Causal effect of pay:** raw history credits pay with half its true effect; double ML and a randomized pay test each recover it.
- **Production:** a FastAPI quote service in Docker (~1 ms per quote), PySpark pipeline on 360M trips, Bayesian response curves (PyMC), CI/CD.

[Demo](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/) · [Memo](https://github.com/janeruxi1/ridehail-driver-pay-optimization/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/ridehail-driver-pay-optimization)

### 💳 Card Fraud: From a Score to a Decision (real data)
[![CI](https://github.com/janeruxi1/card-fraud-decisioning/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/card-fraud-decisioning/actions) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-card-fraud-decisioning.streamlit.app/)

- **Leakage found first:** a random hold-out would credit the model with 74% of fraud from recognizing repeat fraudsters, versus 16% in later months; every result is on later months.
- **Decision in dollars:** an expected-cost policy costs **$3,496 per 1,000 payments** vs $5,795 for approving all; the decision layer alone saves **$1,070** [95% CI $699–$1,425] with the same model.
- **Monitoring:** recall decays from 40% to 29% in two months and only 29% of labels arrive within a week, so the reviewers' hit rate is the early warning.

[Demo](https://janeruxi1-card-fraud-decisioning.streamlit.app/) · [Memo](https://github.com/janeruxi1/card-fraud-decisioning/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/card-fraud-decisioning)

### 🧪 A/B Testing on Real Experiments: One Test to Rollout, 22,743 as a Programme (real data)
[![CI](https://github.com/janeruxi1/ab-testing-real-experiments/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ab-testing-real-experiments/actions) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ab-testing-project.streamlit.app/)

- **One test, plan to rollout:** with the analysis plan committed first, the men's e-mail lifts spend **+$0.77 per customer** (95% CI +0.48 to +1.05), about $207 per 1,000 e-mailed; a segment-targeting policy that won the search failed on held-out customers.
- **A check that finds a real bug:** a routine sample-ratio check, not told the dates, flags **70%** of headline tests in Upworthy's known broken-randomization window and 0.5% outside it.
- **The winner's curse, measured:** only **47%** of a winning headline's lift survives on fresh traffic; empirical-Bayes shrinkage predicts most of the drop, and testing still beat a random headline by 20%.

[Demo](https://janeruxi1-ab-testing-project.streamlit.app/) · [Memo](https://github.com/janeruxi1/ab-testing-real-experiments/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/ab-testing-real-experiments)

### 💸 Churn and Retention Offers: KKBox Subscriptions and a Real Retention Experiment (real data)
[![CI](https://github.com/janeruxi1/churn-uplift-decisioning/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/churn-uplift-decisioning/actions) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-churn-uplift-decisioning.streamlit.app/)

- **Churn model tested out of time:** trained on February 2017, scored once on March; LightGBM reaches **PR-AUC 0.594** against a 9.0% churn rate and its top 10% of scores hold **60%** of churners, after proving no future data leaks into the features; every model run is tracked in MLflow and the shipped model registered.
- **A "randomized" experiment that wasn't:** in a real telecom retention campaign, a model predicts who was called (AUC 0.64); propensity-weighted, doubly robust estimates show **no detectable effect** (−0.49 points, 95% CI −1.49 to +0.51), and no uplift model beats random calling.
- **Decision:** don't roll out an offer on borrowed evidence; it would pay for ~11,000 of 971,000 members at the best estimate, so test it first, on 256 high-risk members per arm.

[Demo](https://janeruxi1-churn-uplift-decisioning.streamlit.app/) · [Memo](https://github.com/janeruxi1/churn-uplift-decisioning/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/churn-uplift-decisioning)

### 🏨 Hotel Search Ranking: Expedia Search Logs (real data)
[![CI](https://github.com/janeruxi1/Hotel-Search-Ranking/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/Hotel-Search-Ranking/actions) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-hotel-search-ranking.streamlit.app/)

- **Causal effect from logs:** randomly ordered searches show reading ranked traffic overstates position effects **3.4×** (95% CI 3.2–3.7); moving from position 10 to 1 is worth a $56 price cut.
- **Decision:** under a rule committed before evaluation, "cheapest first" loses 24% of booking value; the test is sized so the value guardrail sets the sample (616k searches per arm).
- **Learning to rank:** LightGBM LambdaMART beats the choice model (+0.021 position-adjusted NDCG on the same attributes), after a correction for a tilt in the "random" searches that had overstated the feature gain by half.

[Demo](https://janeruxi1-hotel-search-ranking.streamlit.app/) · [Memo](https://github.com/janeruxi1/Hotel-Search-Ranking/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/Hotel-Search-Ranking)

### 🧮 Product Analytics in SQL: Six E-commerce Cases on BigQuery
[![CI](https://github.com/janeruxi1/ecommerce-sql-product-analytics/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ecommerce-sql-product-analytics/actions)

- **Revenue drop, diagnosed:** January revenue fell 64.3%; a quarter of purchases arrived without revenue, so much of the drop is tracking, and a shift-share split shows the rest is site-wide.
- **A readout that refuses to be fooled:** an A/B readout written in SQL finds a "significant" +3.6-point win that the planted truth (+0.26), the 4.4-point MDE and a 200-split A/A check all show is noise.
- **Core SQL:** ordered funnels, sessionization with `LAG`, cohort grids, a north-star metric tree, `UNNEST` of GA4's nested events, each query tested in CI.

[Code and cases](https://github.com/janeruxi1/ecommerce-sql-product-analytics)

### 🔎 RAG Evaluation: StreamFlix Support Assistant
[![CI](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml) [![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/)

- **Golden set first:** 120 questions written before any retrieval code, 25 of them unanswerable; the cited prompt refused 25 of 25 with 0 fabricated citations, which only bounds the true rate at 86.7%, so the memo recommends a pilot.
- **Judge validated before use:** `gpt-4o` passed a 9-case gate and a bias audit; BM25 was not beaten by a transformer across 64 configurations.
- **Ticket routing in PyTorch:** a fine-tuned BGE-small router on 3,080 real support questions; across three seeds its edge over frozen embeddings was calibration (ECE 0.016 vs 0.106), not accuracy.

[Demo](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/) · [Memo](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/blob/main/reports/decision_memo.md) · [Code](https://github.com/janeruxi1/StreamFlix-RAG-evaluation)

---

## 🛠️ Skills
- **Causal inference and experimentation:** DiD and event studies, HonestDiD, synthetic control, double ML, uplift; power analysis, SRM, CUPED, Bayesian A/B, switchback and multi-arm test design
- **ML:** LightGBM/XGBoost, learning to rank, PyTorch fine-tuning, calibration, SHAP, survival analysis, forecasting with backtests, LLM evaluation
- **Decision science:** expected-cost policies, budget allocation, mixed-integer optimization, simulation, offline policy evaluation
- **Data and engineering:** Python, SQL (BigQuery, DuckDB), PySpark, AWS (S3, Athena, CloudFormation), FastAPI, Docker, MLflow, pytest, GitHub Actions
- **At work:** Databricks, SQL Server, Oracle, Power BI, Tableau

---

## 🎯 How I work
- **Start from the decision.** Agree the question, the metric and the guardrails before touching the data.
- **Try to break my own result.** Placebos, fake dates, backtests and known-truth simulations before reporting a number.
- **Report uncertainty in plain words.** "No detectable effect" and "not measurable" are answers too.

📫 [LinkedIn](https://www.linkedin.com/in/xiru) · [Email](mailto:ruthruxi@gmail.com) — if you're hiring for experimentation, causal inference, pricing, marketplace, risk or applied ML work, I'd be glad to talk.
