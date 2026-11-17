# Credit default risk model

A model that estimates default risk for existing credit-card accounts at a fixed point in time, and weighs the cost of each kind of mistake, served live from AWS. It is not for approving new loans.

## Data

Default of Credit Card Clients (UCI, CC BY 4.0): 30,000 existing accounts with April–September 2005 payment/bill history and a default flag. State the prediction time and feature availability. Error costs are teaching assumptions in declared units.

- [Default of Credit Card Clients (UCI, CC BY 4.0)](https://archive.ics.uci.edu/dataset/350/default+of+credit+card+clients)

Built step by step on the [Stacc Data Science roadmap](https://app.getstacc.org/learn/ds). Each module adds one verified
milestone to this repository; the commit history is the build log.

## Milestones

| # | Module | Adds to this repo | Verified |
|---|---|---|---|
| 01 | ML Fundamentals | Write a one-page design doc and who uses the prediction, when it is made and what each mistake costs, then train two baseline pipelines. | ☐ |
| 02 | How Models Learn | Train five model families on the same folds, explain how each decides and pick a challenger to carry forward. | ☐ |
| 03 | Feature Engineering | Build preprocessing inside the pipeline, check for leakage and keep only the feature groups that earn their place. | ☐ |
| 04 | Unsupervised Learning | Reduce the bill and payment columns with PCA, group accounts with k-means and test whether the segment helps the model. | ☐ |
| 05 | Model Evaluation | Pick a threshold by cost, check the probabilities are calibrated and compare errors across groups. | ☐ |
| 06 | A/B Testing | Plan a test of a reminder for at-risk accounts: hypothesis, sample size, stopping rule and ship rule. | ☐ |
| 07 | Advanced Models | Compare a boosted tree model with your baseline on cost, speed and explainability, then decide whether to ship it. | ☐ |
| 08 | Model Deployment | Serve the model through a tested FastAPI app, run it in Docker locally, then put it live on AWS Lambda with a public URL. | ☐ |
| 09 | Data Science Capstone | Release the model live with green CI, a model card, one final test, an updated design doc, review rules and a decision memo. | ☐ |

## Acceptance evidence

Use the guided fixture and the independent variation in each module. Fix failures, then rerun every earlier test on the same candidate commit.
The filenames below are the submission contract, not supplied solutions. Implement the tests and artifacts yourself; do not commit generated caches or personal data.

Each list is exactly what Check my work looks for, including the section headings each file needs.

### ML Fundamentals

Task: https://app.getstacc.org/roadmap/ds-ml

- `framing.md` with sections: User, Target, Prediction time, Cost of errors, Baseline
- `src/train.py`
- `tests/test_train.py`
- `tests/test_split_isolation.py`
- `docs/design.md` with sections: Components, Data flow, Failure modes, Cost
- GitHub Actions job `test` passes on the submitted commit

### How Models Learn

Task: https://app.getstacc.org/roadmap/ds-models

- `src/compare_models.py`
- `reports/model_comparison.md` with sections: Models, Cross-validation, How each decides, Choice
- `tests/test_compare_models.py`
- GitHub Actions job `test` passes on the submitted commit

### Feature Engineering

Task: https://app.getstacc.org/roadmap/ds-features

- `src/features.py`
- `reports/feature_ablation.md` with sections: Leakage audit, Ablation results, Decision
- `tests/test_features.py`
- GitHub Actions job `test` passes on the submitted commit

### Unsupervised Learning

Task: https://app.getstacc.org/roadmap/ds-unsupervised

- `src/segments.py`
- `reports/segments.md` with sections: PCA, Choosing k, Segment profiles, Model impact
- `tests/test_segments.py`
- GitHub Actions job `test` passes on the submitted commit

### Model Evaluation

Task: https://app.getstacc.org/roadmap/ds-evaluation

- `evaluation.md` with sections: Baseline, Cross-validation, Threshold, Calibration, Error slices, Final test
- `src/evaluate.py`
- `tests/test_evaluation.py`
- GitHub Actions job `test` passes on the submitted commit

### A/B Testing

Task: https://app.getstacc.org/roadmap/ds-experiments

- `experiment_spec.md` with sections: Hypothesis, Randomisation unit, Primary metric, Guardrails, Sample size, Stopping rule, Decision rule
- `tests/test_experiment_simulation.py`
- GitHub Actions job `test` passes on the submitted commit

### Advanced Models

Task: https://app.getstacc.org/roadmap/ds-deeplearning

- `model_selection.md` with sections: Baseline, Quality, Latency, Interpretability, Cost, Ship decision
- `tests/test_model_comparison.py`
- GitHub Actions job `test` passes on the submitted commit

### Model Deployment

Task: https://app.getstacc.org/roadmap/ds-deployment

- `app/main.py`
- `tests/test_api.py`
- `docs/api.md` with sections: Endpoints, Validation, Latency
- `Dockerfile`
- `README.md` with sections: Live
- GitHub Actions job `test` passes on the submitted commit
- the link under the README Live section answers when checked (a health endpoint)

### Data Science Capstone

Task: https://app.getstacc.org/roadmap/ds-llm

- `README.md` with sections: Decision, Reproduce, What broke, Walkthrough, Live
- `MODEL_CARD.md` with sections: Intended use, Limitations, Evaluation
- `reports/final_test.md` with sections: Protocol, Result, Limitations
- `reports/decision_memo.md` with sections: Recommendation, Evidence, Risk, Next action
- `tests/test_release_acceptance.py`
- `reports/release_scenarios.md`
- `docs/design.md` with sections: What changed, At 10x
- GitHub Actions job `test` passes on the submitted commit
- README Walkthrough section links an HTTPS demonstration
- the link under the README Live section answers when checked (a health endpoint)

Keep the assessment job named `test` in GitHub Actions. It must run the actual acceptance tests; a green empty workflow does not establish correctness.
For non-Python artifacts, add the appropriate validation/integration commands to CI and retain their outputs.
Stacc's automatic checks establish artifact structure and CI status. Use the module criteria to assess numerical correctness, design quality and independent understanding.

Tick a row when Stacc verifies the milestone. Replace this section's intro, but keep the table:
the first milestone checks that the plan is here.

<!--
Final demo question (answer it in the capstone walkthrough):
How does your model score an account, why did you pick that threshold, where is it less sure, and can someone else reproduce it? Explain why it cannot be used to approve new loans.

The capstone requires a "## Walkthrough" section in this README linking a
walkthrough of five minutes or less, and CI passing on the submitted commit.
-->
