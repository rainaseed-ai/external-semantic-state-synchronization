# Table of Contents

1. Introduction  
   問題設定と背景

2. Synchronization Model（理論の中心）
   - Seed（External Semantic State）
   - Drift（Deviation Model）
   - Manual Sync（Human-in-the-loop）
   - State Transition（Reinitialization）

3. Operational Architecture（構造図）
   Human → External State → LLM A → External State → LLM B

4. Case Studies（Semantic Continuity）
   Gemini → Copilot → Gemini  
   ※人格ではなく「意味的一貫性」として扱う

5. Evaluation（定性＋半定量）
   - Seed Reinitialization
   - Drift Recovery
   - Cross-Platform Continuity
   - Human Intervention Robustness

6. Discussion
   - Limitations
   - Generalizability
   - Threats to Validity
   - Comparison with Existing Approaches
   - Future Automation

7. Conclusion  
   External State Synchronization の価値

---

# Appendices

A. Synchronization Examples（同期ログ）  
   - A.1 Thread Transition with External Summary  
   - A.2 Drift Detection and Seed Reconstruction  
   - A.3 External State Tracking Behaviors  
   - A.4 Summary  

B. Seed Templates（Seedの構造例）  
   - B.1 Minimal Seed  
   - B.2 Extended Seed  
   - B.3 Recovery Seed  
   - B.4 Notes on Seed Portability  

C. Evaluation Rubrics（評価指標）  
   - C.1 Semantic Continuity Assessment (SCA)  
   - C.2 Drift Magnitude Index (DMI)  
   - C.3 Recovery Assessment (RA)  
   - C.4 Cross‑Platform Alignment Assessment (CPAA)  

D. Additional Case Studies（追加ケース）  
   - D.1 Long‑Horizon Drift Patterns  
   - D.2 Timing Differences in Seed Reinjection  
   - D.3 Platform Variation Observations  
   - D.4 Extended Interaction Logs  

E. Supplementary Concept: The Anocator Role（補助概念）  
   - E.1 Definition  
   - E.2 Operational Behaviors  
   - E.3 Relation to External Semantic State  
   - E.4 Notes on Human‑in‑the‑Loop Synchronization  

F. Research Limitations and Future Directions  
   （研究の限界と今後の展望）

Z. Transparency Statement（透明性表明）
