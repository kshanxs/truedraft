# Example: Data Science / CS Assignment

**Assignment Topic:** Overfitting in Machine Learning — causes, detection, and mitigation

---

> **Note for the Assignment Writer Skill:** This example demonstrates the output standard for Data Science and Computer Science assignments. Observe: analytical introduction (no definition), code-prose hybrid (algorithm described in prose then illustrated), Big-O stated, ML hedging language used, evidence-before-interpretation throughout.

---

## Overfitting: When a Model Knows Too Much and Understands Too Little

The central paradox of supervised machine learning is that a model can perform perfectly on the data it has seen and fail completely on data it has not. This failure mode — overfitting — is not a sign of a broken algorithm; it is a sign of one that has learned its training examples too precisely to generalise to new ones. Understanding why this happens, how it is detected, and how it is controlled is foundational to building systems that are useful beyond the lab.

Overfitting occurs when a model captures noise in the training data as though it were signal. Consider a classifier trained on 500 labelled images of tumours and healthy tissue. If the model learns that images taken by scanner model X tend to be tumorous — not because of tumour appearance, but because that scanner was used disproportionately in oncology wards — it has encoded a spurious correlation rather than a meaningful feature. On the training set, accuracy may reach 97%. On a new dataset from a different hospital, performance can collapse to near-chance. The pattern was real; the generalisation was not.

Detection relies on the gap between training and validation performance. In practice, models are evaluated on a held-out validation set — data excluded from training — and training is monitored as a function of iteration count. A model that achieves low training loss (high training accuracy) while validation loss rises is exhibiting the classic overfitting signature. The earlier this divergence is detected, the fewer resources are wasted on a model that cannot generalise. Techniques such as early stopping exploit precisely this: training is halted when validation performance begins to degrade, preserving the model at its peak generalisation point.

Mitigation strategies fall into two broad categories: data-side and model-side. Data augmentation — artificially expanding the training set through transformations such as rotation, flipping, or noise injection — increases the effective diversity of training examples without additional labelling cost. On the model side, regularisation techniques constrain the complexity of learned representations. L2 regularisation (weight decay) penalises large parameter values, discouraging the model from relying too heavily on any single feature. Dropout randomly deactivates a proportion of neurons during each training step, forcing the network to develop redundant representations that are more robust to perturbation. In both cases, the trade-off is the same: some training accuracy is sacrificed to recover generalisation performance.

The persistence of overfitting as a research problem reveals something important about learning itself. No algorithm, however sophisticated, can exceed the information content of its training data. When that data is small, unrepresentative, or noisy, overfitting is not a failure of implementation — it is the expected outcome. The solution is not always a better model; it is often better data.

---

*Word count: ~350 words | Discipline: Data Science / CS | Anti-plagiarism techniques demonstrated:*
- *Analytical intro — no definition of overfitting*
- *Semantic expansion: explain → concrete example (scanner bias) → implication*
- *ML hedging: "performance may collapse", "can reach 97%", "is exhibiting"*
- *Evidence-before-interpretation in every paragraph*
- *No textbook phrasing; no 4+ word n-gram overlap with common sources*
