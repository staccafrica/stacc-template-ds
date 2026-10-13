# Credit Risk Underwriting & Default Decision System

An institutional credit risk decision system that approves creditworthy borrowers while strictly minimizing expected loss from loan defaults under asymmetric error consequences ($10k FN vs $500 FP).

## Data

Default of Credit Card Clients (UCI, CC BY 4.0): 30,000 accounts with a default flag. The $10k and $500 error costs are assumptions you write in framing.md.

- [Default of Credit Card Clients (UCI, CC BY 4.0)](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)

Built step by step on the [Stacc Data Science roadmap](https://app.getstacc.org/learn/ds). Each module adds one verified
milestone to this repository; the commit history is the build log.

## Milestones

| # | Module | Adds to this repo | Verified |
|---|---|---|---|
| 01 | ML Fundamentals | Frame the economic loss matrix ($FN vs $FP), prediction moment, and build baseline scikit-learn pipelines. | ☐ |
| 02 | Feature Engineering | Build leakage-proof preprocessing (ColumnTransformer) and audit cross-validated feature ablation. | ☐ |
| 03 | Model Building & Evaluation | Optimize decision threshold by expected monetary value ($EMV); calibrate default probabilities and audit subgroup fairness. | ☐ |
| 04 | Experimentation & A/B Testing | Design an online champion-challenger A/B experiment protocol to safely evaluate the new credit policy. | ☐ |
| 05 | Model Deployment | Package the calibrated model into a containerized FastAPI scoring microservice with input schema validation. | ☐ |
| 06 | Advanced Modeling | Benchmark gradient boosted trees against the linear credit scorecard, evaluating latency, interpretability (SHAP), and added complexity. | ☐ |
| 07 | End-to-End Decision System | Release the complete credit risk decision engine with green CI, model card, automated drift monitoring, governance, and stakeholder memo. | ☐ |

Tick a row when Stacc verifies the milestone. Replace this section's intro, but keep the table:
the first milestone checks that the plan is here.

<!--
Final demo question (answer it in the capstone walkthrough):
At loan application time, how does the model balance expected default loss against lost customer revenue, and what operational audit evidence proves it is calibrated, fair, and reliable?

The capstone requires a "## Walkthrough" section in this README linking a
walkthrough of five minutes or less, and CI passing on the submitted commit.
-->
