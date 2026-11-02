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

### ML Fundamentals

- `framing.md`
- `src/train.py`
- `tests/test_train.py`
- `tests/test_split_isolation.py`
- `docs/design.md`

### How Models Learn

- `src/compare_models.py`
- `reports/model_comparison.md`
- `tests/test_compare_models.py`

### Feature Engineering

- `src/features.py`
- `reports/feature_ablation.md`
- `tests/test_features.py`

### Unsupervised Learning

- `src/segments.py`
- `reports/segments.md`
- `tests/test_segments.py`

### Model Evaluation

- `evaluation.md`
- `src/evaluate.py`
- `tests/test_evaluation.py`

### A/B Testing

- `experiment_spec.md`
- `tests/test_experiment_simulation.py`

### Advanced Models

- `model_selection.md`
- `tests/test_model_comparison.py`

### Model Deployment

- `app/main.py`
- `tests/test_api.py`
- `docs/api.md`
- `Dockerfile`
- `README.md`

### Data Science Capstone

- `README.md`
- `MODEL_CARD.md`
- `reports/final_test.md`
- `reports/decision_memo.md`
- `tests/test_release_acceptance.py`
- `reports/release_scenarios.md`
- `docs/design.md`

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
