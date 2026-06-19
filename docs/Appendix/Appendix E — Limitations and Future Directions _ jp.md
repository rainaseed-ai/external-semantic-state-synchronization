## Appendix E — Limitations and Future Directions
**（研究の限界と今後の展望）**

※本 Appendix は、本文 Chapter 6 の議論を補完する目的で、研究の限界と今後の課題を詳細化したものである。

### E.1 Limitations（研究の限界）

本研究は、外部意味状態同期（External Semantic State Synchronization）の 観測・定義・評価指標化を試みたものであるが、 以下の限界が存在する。

#### E.1.1 モデル依存性（Model Dependence）
本研究で観測された同期現象は、 特定の LLM（Copilot / Gemini / ChatGPT）に基づくものであり、 他モデルに対して一般化可能である保証は限定的である。

#### E.1.2 Drift の不可避性（Inevitable Drift）
長期対話における Drift は完全には回避できず、 Seed による補正もタイミング依存性を持つ（Appendix D‑2）。

#### E.1.3 外部観測の限界（Limits of External Observation）
本研究はすべて外部観測に基づくため、 内部表現（Internal Representation）を直接検証することはできない。

#### E.1.4 ユーザー依存性（User‑Dependent Variability）
Seed の効果はユーザーの文体・安定性・入力の一貫性に依存し、 完全にモデル側の特性として切り離すことはできない。

### E.2 Future Directions（今後の課題）

#### E.2.1 Seed 設計の最適化（Seed Optimization）
Seed の構造・長さ・抽象度が同期に与える影響を 体系的に評価する必要がある。

#### E.2.2 Drift 予測モデル（Drift Prediction Model）
DMI（Drift Magnitude Index）を用いた **Drift の事前予測モデル**の構築が今後の課題となる。

#### E.2.3 プラットフォーム横断同期の一般化（Cross‑Platform Generalization）
Appendix D‑3 の観測を踏まえ、 異なる LLM 間での同期再現性を より大規模に検証する必要がある。
E.2.4 長期安定化アルゴリズム（Long‑Term Stabilization）
長期対話における Drift の蓄積を抑制する
 **安定化アルゴリズム**（**Stabilization Algorithm**）の設計が求められる。
