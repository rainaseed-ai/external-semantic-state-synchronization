## Appendix E — Limitations and Future Directions

### E.1 Limitations

This study attempts to observe, define, and evaluate External Semantic State Synchronization, but several limitations remain:

#### E.1.1 Model Dependence

Findings are based on specific LLMs, and generalization to other models is limited.

#### E.1.2 Inevitable Drift

Long‑horizon Drift cannot be fully avoided, and Seed‑based correction exhibits timing‑dependent behavior.

#### E.1.3 Limits of External‑Only Observation

Because this study relies solely on external observation, internal representations cannot be directly verified. Future advances in **hidden‑state visualization** may enable deeper validation of the proposed framework.

#### E.1.4 Operator‑Dependent Variables

Synchronization stability depends on user consistency and style, reflecting **Human‑in‑the‑loop variability** that cannot be fully separated from model behavior.


### E.2 Future Directions

#### E.2.1 Seed Optimization

Systematic evaluation of Seed structure, length, and abstraction.

#### E.2.2 Drift Prediction & Auto‑Correction

Development of **Drift prediction models** using DMI, and foundational work toward **automatic intervention.**

#### E.2.3 Cross‑Platform Generalization

Large‑scale validation across different LLM platforms.

#### E.2.4 Long‑Term Stabilization Algorithms

Design of algorithms to suppress cumulative Drift in long‑horizon interactions.