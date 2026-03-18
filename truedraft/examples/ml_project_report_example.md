# Example: End-to-End ML Project Report (Mixed Mode)

**User Prompt:**
> "Help me write my university ML project report on customer churn prediction. Include implementation and evaluation sections, and keep placeholders for missing citations."

---

## Mode Detected

`mixed` (report + implementation)

Pipeline path:

1. `plan`
2. `outline`
3. `draft`
4. `coding`
5. `rewrite`
6. `audit`

---

## Claim Plan (Condensed)

- Thesis: A gradient-boosted tabular pipeline can improve churn prediction utility versus a logistic baseline when class imbalance and thresholding are handled explicitly.
- Section goals:
  - define business and technical objective
  - justify dataset handling and preprocessing
  - compare baseline vs tuned model
  - interpret tradeoffs using precision, recall, and calibration context
- Examples to avoid: generic "AI transforms business" claims, unsupported benchmark claims.
- Source placeholders:
  - `[CITE: churn modeling benchmark paper]`
  - `[CITE: gradient boosting reference]`
  - `[CITE: calibration / threshold tuning reference]`

---

## Outline (Approved)

1. Introduction
2. Related Work
3. Data and Methodology
4. Implementation
5. Evaluation and Results
6. Limitations
7. Conclusion
8. References (placeholders if needed)

---

## Draft Excerpt (Report Sections)

### Introduction

Customer churn prediction is operationally valuable only when model outputs can support intervention decisions at realistic precision-recall tradeoffs, not merely maximize headline accuracy. This report evaluates whether a gradient-boosted classifier can improve decision utility over a logistic baseline on a structured telecom churn dataset while preserving interpretability at the feature level.

Rather than treat performance as a single score, the analysis focuses on threshold-dependent behavior, calibration quality, and class-imbalance handling. This framing is necessary because churn datasets are typically skewed and can produce optimistic accuracy under poor minority-class detection `[CITE: churn modeling benchmark paper]`.

### Data and Methodology

The dataset contains customer account, usage, and service attributes with binary churn labels. The split strategy uses stratified 80/10/10 partitions to preserve churn prevalence across train, validation, and test sets. Missing-value handling and categorical encoding are applied through a reproducible preprocessing pipeline.

Model development compares:

- baseline: regularized logistic regression
- candidate: gradient-boosted decision trees

Hyperparameter selection is performed on validation F1 and PR-AUC, followed by threshold tuning based on intervention capacity assumptions.

---

## Coding Stage Output (Implementation + Evaluation)

### Implementation Design

The pipeline separates data preparation, model training, and evaluation so that each stage can be tested independently. A `ColumnTransformer` applies one-hot encoding to categorical fields and robust scaling to selected numeric fields. This transformed feature space is shared by both baseline and boosted models to isolate model-choice effects.

### Model / Pipeline Choices

- Baseline: logistic regression with class weighting.
- Candidate: gradient boosting (tree depth and learning rate tuned via validation search).
- Selection criterion: PR-AUC and F1 at operational threshold, not accuracy alone.

### Evaluation Metrics

- PR-AUC
- F1 score
- recall at chosen threshold
- calibration error (reported qualitatively if full calibration stats are unavailable)

### Pseudocode (Condensed)

```python
def train_and_compare(train_df, val_df, test_df):
    preprocessor = build_preprocessor()

    baseline = build_logistic_model()
    boosted = build_gradient_boosted_model()

    baseline_pipeline = Pipeline([("prep", preprocessor), ("model", baseline)])
    boosted_pipeline = Pipeline([("prep", preprocessor), ("model", boosted)])

    fit(baseline_pipeline, train_df)
    fit(boosted_pipeline, train_df)

    baseline_metrics = evaluate(baseline_pipeline, val_df)
    boosted_metrics = evaluate(boosted_pipeline, val_df)

    selected = choose_model(baseline_metrics, boosted_metrics, objective="pr_auc_f1")
    tuned_threshold = tune_threshold(selected, val_df)

    return evaluate_with_threshold(selected, test_df, tuned_threshold)
```

### Complexity and Runtime Notes

- Logistic training complexity is approximately linear in samples and features per optimization pass.
- Boosting increases training cost due to sequential tree fitting but often improves minority-class capture.
- Inference remains feasible for batch scoring in coursework-scale datasets.

### Limitations and Risks

- Reported performance is dataset-specific and may not generalize to other customer populations.
- Threshold recommendations depend on intervention budget assumptions.
- Any missing benchmark comparisons remain placeholders until sources are supplied.

---

## Rewrite Actions (Condensed)

- Introduction: `light edit` (tightened opening, removed generic wording)
- Methodology: `rewrite now` (reduced boilerplate phrasing)
- Implementation: `leave` (already specific and structured)

---

## Audit Note

Trust level: `medium-high` (mixed mode with concrete implementation details).

Unresolved support gaps:

- `[CITE: churn modeling benchmark paper]`
- `[CITE: gradient boosting reference]`
- `[CITE: calibration / threshold tuning reference]`

Delivery status: **Not submission-ready until placeholders are resolved.**
