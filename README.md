### Contradictions break AI. Here's the math.

LLMs degrade in long conversations. Everyone assumes it's a context length problem. **It's not. It's contradiction accumulation.**

GPT-4o-mini: 100% → 10%. Gemini: 100% → 0%. Google's 1M-token window? Still −47.8pp under contradiction. Removing contradictions restores accuracy. Expanding the window doesn't.

The framework generates testable predictions. The multi-attractor extension predicts Gemini's accuracy follows **P = 1/(1+K/L)** — derived from 3 data points, confirmed at 5 context lengths (32K–512K) with **MAE 2%**, two out-of-sample predictions within 1%. Full chain: axioms → Lean 4 proof → prediction → experiment.

I built an **external metabolism layer** that resolves contradictions during idle time, analogous to memory consolidation during sleep. Result: **+52.2pp accuracy** (n=3, Kruskal-Wallis p=0.027; 8-model sign test p=0.0107). Unexpected: the metabolized system *exceeds* the contradiction-free baseline.

---

### 🧬 Projects

**[delta-prune](https://github.com/karesansui-u/delta-prune)** — Scan & clean contradictions before sending to any LLM API. 3 lines of code. [![PyPI](https://img.shields.io/pypi/v/delta-prune)](https://pypi.org/project/delta-prune/)

```python
from delta_prune import DeltaPrune
prune = DeltaPrune(llm=OpenAILLM())
result = prune(messages)  # contradictions resolved
```

**[DeltaZero](https://github.com/karesansui-u/delta-zero)** — Full metabolic architecture. 4-layer memory, temporal integration, survival equation monitoring. The research system behind the papers.

**[DeltaLint](https://github.com/karesansui-u/delta-lint)** — Structural contradiction scanner for codebases. Finds where one module's assumptions contradict another's behavior.

---

### 📄 Papers

> **"Context rot is not a length problem. It's a contradiction problem."**

| # | Title | Key Result | DOI |
|---|-------|-----------|-----|
| 1 | **Structural Collapse as Information Loss** | S = μ × e^{-δ}: contradiction → exponential decay. Multi-attractor prediction confirmed (K=19.5±3.4, MAE 2%, 5 context lengths). Lean 4 verified (sorry=0). | [Zenodo](https://zenodo.org/records/19254667) |
| 2 | **Predicting Computational Cost from δ** | Same δ governs both solution existence and computational cost. Sensitivity exponent is solver-dependent. | [Zenodo](https://zenodo.org/records/18943573) |
| 3 | **Contradiction Metabolism for LLMs** | External metabolism prevents context rot. +52.2pp (n=3, p=0.027; 8-model sign test p=0.0107). Metabolized system exceeds contradiction-free baseline. | [Zenodo](https://zenodo.org/records/19322371) |

🔬 [Lean 4 formal proofs](https://github.com/karesansui-u/delta-survival-papers/tree/main/lean) — 160 propositions, `sorry = 0`, `axiom = 0`

📦 [OSF Project](https://osf.io/mdh7b/) — All papers, data, and code in one place

---

Software engineer, Japan
