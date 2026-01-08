🔍 Early Warning System for Employee Attrition

Behavioral Risk Analytics + Explainable Machine Learning

📌 Project Overview

Employee attrition is rarely sudden—it is typically preceded by weeks of behavioral signals such as workload escalation, boundary erosion, and reduced recovery.
This project builds an early warning system that detects attrition risk 6–10 weeks in advance using time-series behavioral analytics and validates these signals with interpretable machine learning.

Rather than treating attrition as a binary classification problem, the system produces continuous risk scores and probabilistic alerts that support proactive intervention.

🧠 Key Contributions

Engineered a time-aware behavioral dataset (17,640 employee-week records)

Modeled behavioral dynamics including:

Workload pressure

Boundary erosion

Recovery deficits

Behavioral volatility

Designed an explainable risk score decomposed into actionable components

Visualized early warning signals and intervention tradeoffs

Trained a probabilistic ML model to validate and automate risk detection

Implemented threshold-based decision logic for real-world use

📊 Data & Feature Engineering
Layer 1 — HR Attributes

Job satisfaction

Work-life balance

Overtime

Promotion history

Layer 2 — Behavioral Time-Series (Engineered)

Each employee is modeled weekly across a 12-week window:

Weekly hours & overtime

Meetings per week

After-hours workdays

PTO usage

Fatigue index

Momentum (week-over-week change)

Short-term trends (4-week rolling)

Volatility (behavioral instability)

Explainable Risk Decomposition

Workload Risk

Boundary Risk

Recovery Deficit

Volatility Risk

These components combine into a final Risk Score (0–100).

📈 Visualization & Analytics

The project emphasizes decision-ready analytics, including:

Average risk trajectories leading up to attrition

Individual employee risk timelines

Risk score distributions at intervention points

Intervention coverage vs attrition capture tradeoff

Risk driver decomposition

Correlation matrix for feature validation

These visualizations demonstrate when, why, and how attrition risk emerges.

🤖 Machine Learning Validation

A Logistic Regression model was trained using behavioral features at Week −4 (realistic intervention point).

Why ML is used:

To validate behavioral risk signals

To automate risk ranking

Not as a black-box replacement for analytics

Evaluation Strategy:

ROC-AUC for ranking ability

F1 score for threshold tuning (rare-event aware)

Probability-based decisions instead of binary predictions

🚦 Deployment Logic (How the Model Is Used)

The model operates as a rolling risk scorer:

Weekly behavioral features are updated

Risk score is recomputed

Model outputs attrition probability

Thresholds trigger actions

Example policy:

Probability	Action
< 0.25	Monitor
0.25–0.35	Manager check-in
> 0.35	HR intervention
🧪 Manual Scoring Example

A hypothetical employee at Week −6 was scored:

Predicted Probability: 0.399
Intervention Flag: True


This demonstrates practical, ethical deployment focused on support—not prediction certainty.

🧠 Key Takeaways

Attrition risk is behavioral and dynamic, not static

Volatility and boundary erosion are strong early signals

Explainability is critical for trust and action

ML should support, not replace, analytics

🛠️ Tools & Technologies

Python (pandas, numpy)

matplotlib

scikit-learn

Jupyter Notebook

📌 Future Enhancements

Probability calibration

Class-weighted models

SHAP-based explanations

Integration with HR dashboards
