# Discipline: Data Science & Computer Science

## Load when
The user's course is: Data Science, Computer Science, Machine Learning, Artificial Intelligence, Software Engineering, Statistics, Data Analytics, Databases, Cybersecurity, or any computing/data-focused field.

> **Note:** If the course is a general science or engineering module (biology, chemistry, physics), load `references/disciplines/science.md` instead. Load this file only when the assignment is primarily computational or data-driven.

---

## Structure

### For Project Reports / Technical Reports
```
Problem Statement     ← What problem is being solved and why it matters
Related Work          ← Existing approaches and their limitations
Methodology           ← Design decisions, data sources, algorithm choices
Implementation        ← How it was built; key technical decisions
Evaluation            ← Results, metrics, comparison to baseline
Conclusion            ← Summary + limitations + future work
References
Appendices            ← Code listings, raw data tables (if lengthy)
```

### For Research / Literature Review
```
Introduction → Background → Critical Analysis → Discussion → Conclusion
```

### For Algorithm / Problem-Solving Assignments
```
Problem Restatement → Approach Selection → Implementation → Complexity Analysis → Testing
```

---

## Writing Rules

### Code-Prose Hybrid
When code or pseudocode is included alongside written work:
- **Never let code replace explanation.** Every algorithm or code block must be accompanied by prose describing *what it does* and *why* this approach was chosen.
- Use pseudocode for algorithmic description in the main body; put full implementation in an appendix unless the assignment is primarily coding.
- Refer to code inline: "As shown in Algorithm 1, the merge step runs in O(n) time..."

### Algorithmic Analysis
- **Always state time and space complexity** for any algorithm discussed: O(n log n) time, O(n) space.
- Justify your algorithm choice relative to alternatives: "A hash map was chosen over a sorted array to achieve O(1) average-case lookups at the cost of O(n) additional space."
- Use Big-O notation correctly — specify average, worst, and best case where they differ significantly.

### Dataset Methodology
When data is involved (Data Science, ML, statistics):
- Always describe: **source**, **size**, **key features**, **preprocessing steps**, and any **known biases or limitations**.
- State train/val/test splits and why those ratios were chosen.
- Acknowledge if the dataset is small, imbalanced, or domain-limited.
> ✅ "The dataset comprised 12,000 labelled images (80/10/10 train/val/test split), sourced from [source]. Class imbalance of 3:1 (negative:positive) was addressed using SMOTE oversampling."
> ❌ "The dataset was used to train the model."

### Hedging for ML/AI Claims
Machine learning outputs are probabilistic — avoid overconfident language:
- "The model achieved..." not "The model proved..." or "The model correctly..."
- "Results suggest that..." not "Results show that X is always..."
- "On this dataset, the classifier generalised well to..." not "The classifier is accurate."

### Visualisation and Figure References
- Every figure/chart must be captioned and referenced in the text: "Figure 2 shows the confusion matrix for the test set..."
- Describe what the figure *shows* and *what it means*, don't just label it:
> ✅ "The precision-recall curve (Figure 3) indicates a trade-off at threshold 0.45, where precision drops sharply while recall plateaus, suggesting diminishing returns from further threshold reduction."
> ❌ "The precision-recall curve is shown in Figure 3."

### Quantification
- Report all metrics precisely: accuracy, F1, RMSE, AUC-ROC — not just "the model performed well."
- Include confidence intervals or standard deviation where multiple runs were conducted.
- Use units for computational metrics: runtime in ms/s, memory in MB/GB.

### Voice
- Passive voice is acceptable in methodology: "The data was normalised using min-max scaling..."
- Active voice preferred in discussion and evaluation: "This approach outperformed the baseline by 12% F1."
- Avoid first-person "I" unless the assignment specifically requests a reflective component.

---

## Introduction Rules

Open with the problem context or research gap — never a definition:
> ✅ "Despite widespread adoption of transformer architectures in NLP, their application to structured tabular data remains computationally prohibitive for resource-constrained environments..."
> ❌ "Machine learning is defined as the process by which computers learn from data without being explicitly programmed."

---

## Citation Defaults
- **Preferred:** IEEE (Computer Science, Engineering), APA 7 (Data Science, Statistics), ACM (academic Computer Science research)
- Cite all datasets, libraries, and frameworks: "NumPy (Harris et al., 2020)" not just "we used NumPy"
- Cite algorithm papers, not just textbooks, for novel methods

---

## Originality Notes
The highest-risk areas in CS/Data Science assignments are:
1. **Tutorial replication** — implementations that follow a tutorial step-by-step
2. **Boilerplate code commentary** — comments that describe *what* the code does rather than *why*
3. **Generic methodology sections** — "we trained the model, evaluated it, and compared results"

Counter strategies:
- Document design decisions and tradeoffs: "We chose LSTM over GRU because the sequence length variability in our dataset benefits from the separate memory cell..."
- Write comments that explain *why*, not *what*: `# Using rolling average to dampen noise from sparse daily counts` not `# Calculate average`
- Tie your methodology to your specific dataset or constraints — generic pipelines become original when contextualised
- Use descriptive variable names that reflect domain context: `customer_churn_prob` not `y_pred`
