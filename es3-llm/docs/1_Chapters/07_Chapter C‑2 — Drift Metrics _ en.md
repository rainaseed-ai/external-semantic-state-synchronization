## Chapter C‑2 — Drift Metrics

These drift metrics are supplementary behavioral indicators and are not intended to replace the Drift Magnitude Index defined in the main text.

**Drift** in External Semantic State Synchronization refers to a phenomenon in which the model’s output deviates from the user’s writing style, abstraction level, emotional temperature, or reasoning depth, resulting in a loss of alignment with the external semantic state (Seed). To detect Drift, we define the following four metrics.

### C‑2.1 Style Shift
* **Definition:** 
A phenomenon in which the model’s writing style undergoes an abrupt change from the previously established style.
* **Observation Points:**
    * Sudden shift from polite to casual style.
    * Sudden shift from technical style to overly conversational style.
    * Abrupt changes in sentence endings or tone.
    * Continuous instability or oscillation in writing style.
* **Drift Criterion:** 
When stylistic changes occur repeatedly within 2–3 turns, resulting in a divergence from the user’s style.

---

### C‑2.2 Meta‑Leak
* **Definition:** 
A phenomenon in which internal references that should normally remain abstracted (e.g., cite tags, internal IDs, meta‑structures) appear as raw text in the output.
* **Observation Points:**
    * Exposure of internal tags such as “cite: …”.
    * Output of internal IDs or structural markers that should remain hidden.
    * Unnatural insertion of meta‑information into the text.
* **Drift Criterion:** 
If internal meta‑information is exposed even once, it is immediately classified as Drift.

---

### C‑2.3 Over‑Expressiveness
* **Definition:** 
A phenomenon in which emotional expression or ornamental language self‑amplifies beyond contextual necessity, causing an unnatural rise in expressive intensity.
* **Observation Points:**
    * Excessive increase in enthusiasm relative to the context.
    * Over‑learned amplification of metaphors or decorative expressions.
    * Deviations in emotional tension due to excessive self‑regression of the context.
    * Continuous use of unnecessarily performative or theatrical expressions.
* **Drift Criterion:** 
When the model’s emotional temperature deviates by 2 levels or more from the user’s current state.

---

### C‑2.4 Role Deviation
* **Definition:** 
A phenomenon in which the model abandons the role assigned by the user (e.g., structuring support, technical mode) and exhibits a persona or characterization outside the specified role.
* **Observation Points:**
    * Inability to maintain the assigned role.
    * Excessive characterization of the writing style.
    * Drift from technical mode into casual chat mode.
    * Loss of role‑related information encoded in the Seed.
* **Drift Criterion:** 
When role deviation persists for 1–2 consecutive turns.
