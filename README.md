# 👋 Hi, I'm Xi Ru
**Data Scientist.** I turn experiments, causal analysis, models and forecasts into decisions a business can act on, and I say how sure we are.

📍 Redmond, Washington · 💼 Open to Senior Data Scientist and Data Scientist roles: product, decision science, applied ML, marketplace and pricing · 📫 [ruthruxi@gmail.com](mailto:ruthruxi@gmail.com) · [LinkedIn](https://www.linkedin.com/in/xiru)

---

## ⏱️ The portfolio in one minute

Eight end-to-end projects. Each one starts from a business question, ends with a decision memo, has a live demo, and is checked by CI: tests, a rerun of the analysis, and a check that the numbers in the README and memo match the recorded results.

| Project | The decision | Core methods | Data | Links |
|---|---|---|---|---|
| 🚦 [NYC congestion toll: causal impact](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact) | Should taxi and ride-hail operators offset the new toll? | Difference-in-differences, forecast counterfactual, synthetic control, placebo tests | **Real**: 1.3B NYC trips | [Demo](https://janeruxi1-nyc-congestion-toll-causal-impact.streamlit.app/) · [Memo](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/blob/main/reports/decision_memo.md) |
| 🚕 [Driver pay pricing](https://github.com/janeruxi1/ridehail-driver-pay-optimization) | What should a ride-hail platform pay a driver per trip? | Double ML, Bayesian hierarchical model, mixed-integer optimization, simulation, FastAPI/Docker | **Real**: 360M NYC trips (+ simulated driver choices) | [Demo](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/) · [Memo](https://github.com/janeruxi1/ridehail-driver-pay-optimization/blob/main/reports/decision_memo.md) |
| 💳 [Card fraud decisioning](https://github.com/janeruxi1/card-fraud-decisioning) | Approve, decline or review each payment? | Leakage audit, gradient boosting, calibration, expected-cost policy, drift monitoring | **Real**: 590k payments (IEEE-CIS) | [Demo](https://janeruxi1-card-fraud-decisioning.streamlit.app/) · [Memo](https://github.com/janeruxi1/card-fraud-decisioning/blob/main/reports/decision_memo.md) |
| 🏨 [Hotel search ranking](https://github.com/janeruxi1/Hotel-Search-Ranking) | Which ranking change deserves an A/B test slot? | Causal effect from randomized logs, conditional logit, offline policy evaluation, power analysis | **Real**: 9.9M Expedia impressions | [Demo](https://janeruxi1-hotel-search-ranking.streamlit.app/) · [Memo](https://github.com/janeruxi1/Hotel-Search-Ranking/blob/main/reports/decision_memo.md) |
| 🧪 [A/B test analysis](https://github.com/janeruxi1/StreamFlix-AB-Testing) | Ship the new homepage? | Power analysis, SRM, CUPED, Bayesian A/B, segment effects | Synthetic, with known truth | [Demo](https://janeruxi1-ab-testing-project.streamlit.app/) · [Memo](https://github.com/janeruxi1/StreamFlix-AB-Testing/blob/main/reports/decision_memo.md) |
| 💸 [Churn retention targeting](https://github.com/janeruxi1/StreamFlix-Churn-Retention) | Who gets which retention offer under a budget? | Survival analysis, calibrated churn model, SHAP, uplift models, budget allocation | Synthetic, with known truth | [Demo](https://janeruxi1-streamflix-churn-retention.streamlit.app/) · [Memo](https://github.com/janeruxi1/StreamFlix-Churn-Retention/blob/main/reports/decision_memo.md) |
| 🧮 [Product analytics in SQL](https://github.com/janeruxi1/ecommerce-sql-product-analytics) | Where does checkout leak, why did revenue fall, did the test win? | BigQuery SQL: funnels, sessionization, cohorts, north-star metric, shift-share, A/B readout and A/A in SQL | GA4 sample (real, obfuscated; 4.3M events) + theLook (synthetic) | [Cases](https://github.com/janeruxi1/ecommerce-sql-product-analytics#the-cases) |
| 🔎 [RAG evaluation](https://github.com/janeruxi1/StreamFlix-RAG-evaluation) | Is the LLM support assistant ready for a pilot? | Golden-set design, retrieval bake-off, validated LLM-as-judge, bootstrap inference | Synthetic help centre | [Demo](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/) · [Memo](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/blob/main/reports/decision_memo.md) |

**Short on time?** Read the [congestion toll memo](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/blob/main/reports/decision_memo.md) (causal inference on real data), the [driver pay README](https://github.com/janeruxi1/ridehail-driver-pay-optimization) (modeling through to optimization and a deployed service), and the [fraud decision table](https://github.com/janeruxi1/card-fraud-decisioning#the-decision) (turning a model score into dollars).

---

## 🧭 What a senior data scientist does, and where to see it

| Responsibility | Where to see it |
|---|---|
| **Frame an ambiguous business question** and agree success metrics and guardrails before the analysis | Every project opens with a brief and a decision rule. In hotel ranking and RAG evaluation, the rule was committed to git before the results existed. |
| **Find the causal effect when there is no experiment** | Congestion toll: three methods that check each other, plus seven fake toll dates. Hotel ranking: randomly ordered searches show ranked traffic overstates position effects 3.4×. |
| **Design experiments that answer the decision** | A/B test: power, SRM, CUPED. Hotel ranking: a three-arm test where the guardrail, not the lift, sets the sample size. Driver pay: a switchback test sized on real variation. |
| **Push back on the easy answer** | Congestion toll: the quick comparison shows −2.6%, but the same comparison in a year with no toll shows −4.4%. The memo says "no detectable effect", not "the toll cut trips". |
| **Turn a model into a decision with a dollar value** | Fraud: the decision layer alone saves $1,070 per 1,000 payments with the same model. Churn: budget-capped offers per subscriber. Driver pay: a constrained optimizer with guardrails. |
| **State uncertainty honestly** | Confidence intervals, placebo distributions and backtest error bands on every headline. Results that don't hold up are reported as not measurable. |
| **Build at production scale and quality** | DuckDB, PySpark and AWS Athena pipelines over billions of rows (the congestion toll pipeline runs on S3 + Athena and is reconciled with the local build); a FastAPI service in Docker with CD; CI that reruns every notebook and fails if the results drift. |
| **Communicate to non-technical owners** | A one-page decision memo per project, a live demo a PM can use, and figures labeled in plain language. |
| **Own mistakes in the open** | The RAG project documents a miscounted refusal check and its fix. Hotel ranking documents a bias found in review. Driver pay corrected cleaning rules after the first real month. |

---

## 🌟 Projects

### 🚦 Did NYC's Congestion Toll Cut Taxi and Uber/Lyft Trips? (real data)
[![CI](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/actions)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-nyc-congestion-toll-causal-impact.streamlit.app/)

In January 2025 New York started tolling vehicles entering Manhattan below 60th Street; taxi and Uber/Lyft riders pay a fee on every trip in the zone. Did trips fall? Built on **every TLC trip record from January 2022 to August 2026: 1.3 billion trips**.

- **Answer:** no detectable effect on trips in year one, **+1.0% (95% CI −0.3% to +2.3%)**. All three methods that account for the pre-toll trend land between −0.7% and +2.3%.
- **Why the quick answer is wrong:** a 2025-vs-2024 comparison shows −2.6%, but the same comparison a year earlier, with no toll, shows −4.4%. The zone was already losing trip share before the toll.
- **What the toll did change:** Uber/Lyft trips got 5.0% faster, driver pay per hour on a trip rose 2.7%, and shared-ride requests fell 12.7%.

<details>
<summary><b>Methods, checks and engineering</b></summary>

- **Three methods that check each other:**
  - difference-in-differences with zone and week fixed effects, zone-specific trends and an event study;
  - a forecast counterfactual (LightGBM on regression residuals, four rolling-origin backtests, results net of backtest bias);
  - synthetic control with placebo-in-space p-values.
- **Fake toll dates:** rerunning the main model on seven dates in 2023, when nothing happened, gives "effects" of typically ±4.3%. The claim is therefore "no detectable effect", not "zero".
- **Price sensitivity:** the fee adds 4.3% to a trip's price, and the forecast rules out a price elasticity much stronger than −0.5.
- **Recommendation:** treat the fee as a pass-through. Don't fund promotions to offset it. Test a partial fee refund on shared rides, the one segment that reacted.
- **Engineering:**
  - a DuckDB pipeline turns 168 monthly files into committed daily aggregates;
  - the same pipeline also runs on **AWS (S3 + Athena, infrastructure as CloudFormation)**: 9 queries scan 52 GB for $0.24, and the output matches the laptop build in 504 of 504 checks; the check caught a one-second difference in how the two SQL engines count time, now fixed and tested;
  - CI reruns all six notebooks and fails if any result drifts;
  - a test checks every number quoted in the README and memo.
- Follow-up to the congestion-fee chapter of the driver pay project, which flagged a pre-toll drift it could not resolve.

</details>

🎮 **[Live demo](https://janeruxi1-nyc-congestion-toll-causal-impact.streamlit.app/)** · 📄 **[Decision memo](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact/blob/main/reports/decision_memo.md)** · 👉 **[Code](https://github.com/janeruxi1/nyc-congestion-toll-causal-impact)**

### 🚕 Driver Pay Pricing: NYC Ride-Hailing Marketplace (real data)
[![CI](https://github.com/janeruxi1/ridehail-driver-pay-optimization/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ridehail-driver-pay-optimization/actions)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/)

What should a ride-hailing platform offer a driver for each trip? Pay too little and riders wait and drivers decline; pay too much and the margin disappears. Built on **360 million real trips** (January 2024 – June 2025). Driver accept/decline decisions aren't in the public data, so they are simulated from a known truth, which lets every causal method be checked.

- **Result:** a mixed-integer pay policy earns **+3.7% margin per request** on held-out months, with rider-wait, acceptance and driver-earnings guardrails all met. Cutting pay to the legal floor looks like +27% but breaks all three guardrails.
- **Causal effect of pay:** the raw history credits pay with half its true effect, because premiums go to the trips drivers dislike. Double ML and a randomized pay test each recover the true effect.
- **Production:** a FastAPI quote service in Docker (~1 ms per quote) with a model card, CI on a synthetic city, and CD on merge.

<details>
<summary><b>More detail</b></summary>

- **PySpark pipeline:** 18 monthly files, every cleaning rule counted per month (99.88% of trips kept); two rules were corrected after the first real month.
- **Pay structure:** pay is the legal minimum plus a premium. The premium (7.9% of driver pay) is the lever being priced.
- **Forecasting:** LightGBM by zone and hour with a rolling-origin backtest, 12.7% weighted error against a 6.8% Poisson noise floor. A calibrated long-wait classifier uses a cost-based threshold.
- **Bayesian hierarchical model (PyMC):** gives response curves by segment. The optimizer's guardrails must hold in 20 posterior draws at once.
- **Dispatch simulation:** replays real Brooklyn requests with driver supply calibrated hour by hour. A switchback test is sized with randomization inference.
- **Congestion fee:** traffic in the zone moved 4.6% faster, judged against a placebo distribution. Clustered SEs called 82% of fake start dates "significant". This open question led to the congestion toll project.

</details>

🎮 **[Live demo](https://janeruxi1-ridehail-driver-pay-optimization.streamlit.app/)** · 👉 **[Code](https://github.com/janeruxi1/ridehail-driver-pay-optimization)**

### 💳 Card Fraud: From a Score to a Decision (real data)
[![CI](https://github.com/janeruxi1/card-fraud-decisioning/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/card-fraud-decisioning/actions)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-card-fraud-decisioning.streamlit.app/)

An online merchant must approve, decline or review every card payment, with reviewers for only 1.5% of them. Built on **590,540 real e-commerce payments** (IEEE-CIS).

- **Leakage found first:** fraud labels follow the customer. A random hold-out would credit the model with 74% of fraud from recognizing repeat fraudsters, versus 16% in later months. Every result is therefore measured on later months.
- **Decision, priced in dollars:** an expected-cost policy costs **$3,496 per 1,000 payments**, against $5,795 for approving everything and $4,566 for reviewing the top scores. The decision layer alone saves **$1,070** [95% CI $699–$1,425] with the same model.
- **Guardrail cost made visible:** keeping good-customer declines at the rules' level costs $755 per 1,000 payments, a trade-off for finance to decide.

<details>
<summary><b>More detail</b></summary>

- **Features use only the past:** rebuilding them with everything after three cutoffs deleted changed 0 values.
- **Model:** a calibrated gradient-boosting model finds 35% of fraud [32–38%] in the top 1.5% at 82% precision (logistic regression: 19%). Models were chosen by decision cost, not AUC.
- **Unsupervised anomaly detection:** tested and rejected. Isolation Forest was no better than chance.
- **Monitoring:** recall decays from 40% to 29% in two months, and only 29% of fraud labels arrive within a week. The reviewers' hit rate is the early warning, not the score's distribution.
- **Serving design:** a design for a feature store, live review queue, rules fallback and shadow rollout.

</details>

🎮 **[Live demo](https://janeruxi1-card-fraud-decisioning.streamlit.app/)** · 👉 **[Code](https://github.com/janeruxi1/card-fraud-decisioning)**

### 🏨 Hotel Search Ranking: Expedia Search Logs (real data)
[![CI](https://github.com/janeruxi1/Hotel-Search-Ranking/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/Hotel-Search-Ranking/actions)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-hotel-search-ranking.streamlit.app/)

A ranking team wants to push cheaper hotels up the results. Before spending an A/B slot: how much does position matter, and which ranking should be tested? Built on **9.9M impressions** from Expedia's ICDM 2013 release, 30% of them shown in random order.

- **Causal effect from logs:** the randomly ordered searches show that reading ranked traffic overstates position effects **3.4×** (95% CI 3.2–3.7).
- **Choice model:** a conditional logit written from scratch. Moving from position 10 to 1 is worth a **$56** price cut for clicks.
- **Decision:** with the decision rule committed before evaluation, "cheapest first" loses bookings and 24% of booking value. A three-arm test is sized so the guardrail sets the sample (616k searches per arm).

<details>
<summary><b>More detail</b></summary>

- **SQL:** DuckDB on all 9.9M rows (window functions, `LAG`/`LEAD` checks), each query tested against an independent pandas version.
- **Offline evaluation:** bootstrap and coefficient-draw intervals. Cross-fitting shows the evaluator doesn't flatter its own rankings.
- **Limits:** a check of the mechanism was inconclusive, so the memo recommends a test, not a launch. A bias found during review was fixed and documented.

</details>

🎮 **[Live demo](https://janeruxi1-hotel-search-ranking.streamlit.app/)** · 👉 **[Code](https://github.com/janeruxi1/Hotel-Search-Ranking)**

### 🧪 A/B Test Analysis: StreamFlix Trial-to-Paid Experiment
[![CI](https://github.com/janeruxi1/StreamFlix-AB-Testing/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/StreamFlix-AB-Testing/actions)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-ab-testing-project.streamlit.app/)

From a PM brief to a ship/don't-ship decision on a homepage experiment (synthetic 100k users with a known true effect).

- **Design:** a metric framework (primary, secondary, guardrails) set before analysis, an agreed minimum detectable effect, and a power analysis.
- **Trust checks:** a sample ratio mismatch check, covariate balance, and an engineered assignment bug the analysis has to catch.
- **Inference:** frequentist tests with Holm correction, a Bayesian posterior with ROPE, CUPED, and segment effects with a Simpson's-paradox check.
- **Validation:** the true effect (+2.29pp) falls inside the estimate's interval, and interval coverage is checked by simulation.

🎮 **[Live demo](https://janeruxi1-ab-testing-project.streamlit.app/)** · 👉 **[Code](https://github.com/janeruxi1/StreamFlix-AB-Testing)**

### 💸 Cost-Aware Churn Retention: StreamFlix Subscriber Targeting
[![CI](https://github.com/janeruxi1/StreamFlix-Churn-Retention/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/StreamFlix-Churn-Retention/actions)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-churn-retention.streamlit.app/)

Turns a calibrated churn model into a per-subscriber offer policy under a monthly budget (synthetic 50k subscribers with known uplifts).

- **Impact:** at a $200k monthly budget, replaces a **$252k/month loss** with **+$174k** net expected value (1.87× ROI), a **$426k monthly swing** on less spend.
- **Modeling:** survival analysis and LTV, a four-family model bake-off with Optuna, calibration by segment, and MLflow tracking.
- **Uplift, tested honestly:** a randomized holdout measures the offer's effect. Four uplift learners rank users no better than chance, so the simpler policy ships.

🎮 **[Live demo](https://janeruxi1-streamflix-churn-retention.streamlit.app/)** · 👉 **[Code](https://github.com/janeruxi1/StreamFlix-Churn-Retention)**

### 🧮 Product Analytics in SQL: Six E-commerce Cases on BigQuery
[![CI](https://github.com/janeruxi1/ecommerce-sql-product-analytics/actions/workflows/ci.yml/badge.svg)](https://github.com/janeruxi1/ecommerce-sql-product-analytics/actions)

Six questions a product team asks every quarter, each answered in BigQuery SQL on public data (Google's GA4 Merchandise Store sample and theLook eCommerce), and each query tested on hand-built tables in CI.

- **Revenue drop, diagnosed:** January revenue fell 64.3%; a quarter of January purchases arrived without revenue, so most of the apparent basket-size drop is tracking, and an exact shift-share split shows the rest is site-wide, not one segment.
- **A readout that refuses to be fooled:** an A/B readout written entirely in SQL (sample-ratio check, CUPED, erfc p-values) returns a "significant" +3.6-point win; the planted truth (+0.26), the minimum detectable effect (4.4) and a 200-split A/A check all show it is noise.
- **Core SQL, done carefully:** ordered funnels with inequality joins, sessionization with `LAG` and a `RANGE` frame (ties stay together), cohort grids, a north-star metric tree with trailing-window guardrails, `UNNEST` of GA4's nested events.

👉 **[Code and cases](https://github.com/janeruxi1/ecommerce-sql-product-analytics)**

### 🔎 RAG Evaluation: StreamFlix Support Assistant
[![CI](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/janeruxi1/StreamFlix-RAG-evaluation/actions/workflows/ci.yml)
[![Live Demo](https://img.shields.io/badge/Streamlit-Live%20Demo-FF4B4B?logo=streamlit)](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/)

An evaluation harness and deployment memo for an LLM support assistant over a synthetic 45-article help centre.

- **Golden set first:** 120 questions written before any retrieval code, including 25 the help centre can't answer, so refusal is measured rather than assumed.
- **Evidence over hype:**
  - 64 retrieval configurations compared with paired bootstrap and Holm correction; BM25 was not beaten by a transformer.
  - A pre-registered test found that sending the model every article worked as well as retrieval at this size.
- **Judge validated before use:** `gpt-4o` passed a 9-case gate and a bias audit. The memo recommends a pilot because 25 of 25 refusals only bounds the true rate at 86.7%.

🎮 **[Live demo](https://janeruxi1-streamflix-rag-evaluation.streamlit.app/)** · 👉 **[Code](https://github.com/janeruxi1/StreamFlix-RAG-evaluation)**

---

## 🛠️ Skills and where they're used
- **Causal inference:** difference-in-differences and event studies, synthetic control, forecast counterfactuals, double ML, uplift models, placebo and falsification tests *(congestion toll, driver pay, hotel ranking, churn)*
- **Experimentation:** power analysis, SRM, CUPED, Bayesian A/B, switchback tests, multi-arm test sizing, A/A checks *(A/B test, hotel ranking, driver pay, SQL casebook)*
- **SQL and product analytics:** funnels, sessionization, cohort retention, north-star metrics and guardrails, revenue-drop diagnosis, window functions, nested/array data *(SQL casebook on BigQuery; DuckDB in every real-data project)*
- **ML and forecasting:** LightGBM/XGBoost, calibration, SHAP, survival analysis, rolling-origin backtests, anomaly detection *(fraud, churn, driver pay, congestion toll)*
- **Decision science and optimization:** expected-cost policies, budget allocation, mixed-integer programming, discrete-event simulation, offline policy evaluation *(fraud, churn, driver pay, hotel ranking)*
- **Statistics:** fixed effects, clustered SEs, conditional logit, Bayesian hierarchical models (PyMC), bootstrap, delta method
- **LLM evaluation:** golden sets, retrieval benchmarks, LLM-as-judge validation *(RAG)*
- **Data and engineering:** Python, SQL, R · pandas, DuckDB, PySpark · AWS (S3, Athena, CloudFormation, IAM) · Google BigQuery · Streamlit, FastAPI, Docker, MLflow · pytest, GitHub Actions CI/CD
- **From my day-to-day work** (not in these repositories): Databricks, SQL Server, Oracle, Power BI, Tableau, Flask

---

## 🎯 How I work
- **Start from the decision.** Agree the question, the metric and the guardrails before touching the data.
- **Try to break my own result.** Use placebos, fake dates, backtests and known-truth simulations before reporting a number.
- **Report uncertainty in plain words.** "No detectable effect" and "not measurable" are answers too.
- **Make it reproducible.** Tests, CI, and numbers in the memo that are checked against the code that produced them.

---

## 📫 Get in touch
💼 [LinkedIn](https://www.linkedin.com/in/xiru) · 📧 [Email](mailto:ruthruxi@gmail.com)

If you're hiring for experimentation, causal inference, pricing, marketplace, risk or applied ML work, I'd be glad to talk.
