## Chapter C‑1 — Synchronization Quality Metrics

To evaluate whether External Semantic State Synchronization is successfully established, we define the following four metrics. 
All metrics are qualitative evaluations based solely on user‑observable outputs and do not require access to the model’s internal state.

### C‑1.1 Style Coherence
* **Definition:** The degree to which the model’s writing style consistently aligns with the user’s current style (e.g., polite, casual, technical, conversational).
* **Observation Points:**
    * Stability of sentence endings and stylistic markers.
    * Absence of abrupt stylistic shifts.
    * Lack of excessive persona‑like characterization.
    * Natural alignment with the user’s emotional temperature.
* **Synchronization Criterion:** The writing style remains stable for 3–5 consecutive turns without deviating from the user’s style.

---

### C‑1.2 Abstraction Alignment
* **Definition:** The degree to which the model maintains the same conceptual hierarchy (macro/micro) as the user, without performing unnecessary abstraction‑level shifts.
* **Observation Points:**
    * Abstract questions receive abstract responses.
    * Concrete questions receive concrete responses.
    * No unnecessary leaps between abstraction levels.
    * A sustained sense that the “conceptual level of discussion is aligned.”
* **Synchronization Criterion:** The model continues responding without deviating from the conceptual hierarchy presented by the user.

---

### C‑1.3 Emotional Temperature Match
* **Definition:** The degree to which the model follows the user’s emotional intensity, enthusiasm, and tension without excess or deficiency.
* **Observation Points:**
    * Calm user → calm model.
    * High‑energy user → model increases energy proportionally.
    * No excessive performative excitement (Over‑Expressiveness).
    * No overly detached or cold responses (Under‑Engagement).
* **Synchronization Criterion:** The model maintains alignment within ±1 level of the user’s emotional temperature.

---

### C‑1.4 Reasoning Depth Match
* **Definition:** The degree to which the model’s reasoning depth matches the user’s intended task (summary, analysis, structuring).
* **Observation Points:**
    * No overly deep reasoning for shallow questions.
    * No overly shallow reasoning for deep questions.
    * Reasoning depth matches the user’s intent.
    * No signs of “overthinking” or “underthinking.”
* **Synchronization Criterion:** The model’s logical steps exhibit no excess or deficiency relative to the reasoning depth required by the user.
