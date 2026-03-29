### AI doesn't sleep. That's why it breaks.

LLMs degrade in long conversations. Everyone assumes it's a context length problem. **It's not. It's contradiction accumulation.**

GPT-4o-mini: 100% → 10%. Gemini: 100% → 0%. Google's 1M-token window? Still -47.8pp. Removing contradictions restores accuracy. Expanding the window doesn't.

I built **cognitive sleep for AI** — a metabolism that resolves contradictions during idle time, like human sleep consolidates memory.

**Result**: +52.2pp accuracy improvement across 8 models (p<0.001). 18 patents filed. 8 concepts with zero prior art worldwide.

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
| 1 | **Structural Collapse as Information Loss** | S = μ × e^{-δ}: contradiction causes exponential decay. Validated on SAT + 11 LLM models. Formally verified in Lean 4. | [Zenodo](https://zenodo.org/records/19254667) |
| 2 | **Predicting Computational Cost from δ** | Same δ governs both solution existence and computational cost. Sensitivity exponent is solver-dependent. | [Zenodo](https://zenodo.org/records/18943573) |
| 3 | **Cognitive Sleep for LLMs** | External metabolism prevents context rot. ON vs OFF: +52.2pp (p<0.001, d=8.80). Unexpected: ON exceeds contradiction-free baseline. | [Zenodo](https://zenodo.org/records/19322371) |

🔬 [Lean 4 formal proofs](https://github.com/karesansui-u/delta-survival-papers/tree/main/lean) — 160 propositions, `sorry = 0`, `axiom = 0`

📦 [OSF Project](https://osf.io/mdh7b/) — All papers, data, and code in one place

---

Software engineer, Japan · ORCID: [0009-0008-1306-0316](https://orcid.org/0009-0008-1306-0316)
