## Akihito Sunagawa

LLMs break in long conversations — not because the context is too long, but because **contradictions accumulate**. I'm building the fix.

### Research: Context Rot is a Contradiction Problem

GPT-4o-mini drops from 100% to 10% accuracy under contradiction. Gemini drops to 0%. Even Google's 1M-token window doesn't help (-47.8pp). The only thing that helps is **resolving the contradictions**.

I built a "cognitive sleep" mechanism for LLMs — an external metabolism layer that processes knowledge during idle time, like human sleep consolidates memory. Tested across 8 models: **+52.2pp improvement, p<0.001, d=8.80**.

### Projects

| Project | What it does | Link |
|---------|-------------|------|
| **delta-prune** | 3-line middleware: detect & clean contradictions before sending to any LLM API | [![PyPI](https://img.shields.io/pypi/v/delta-prune)](https://pypi.org/project/delta-prune/) |
| **DeltaZero** | Full metabolic architecture — 4-layer memory, contradiction resolution, survival equation monitoring | [Code](https://github.com/karesansui-u/delta-zero) |
| **delta-lint** | Structural contradiction scanner for codebases | [Code](https://github.com/karesansui-u/delta-lint) |
| **Papers** | 3 papers + Lean 4 formal proofs (160 propositions, sorry=0) | [Papers](https://github.com/karesansui-u/delta-survival-papers) |

### Quick Start

```bash
pip install delta-prune
```

```python
from delta_prune import DeltaPrune
from delta_prune.llm import OpenAILLM

prune = DeltaPrune(llm=OpenAILLM())
result = prune(messages)  # contradictions detected and resolved
```

### Papers

1. **Structural Collapse as Information Loss** — S = μ × e^{-δ} proves contradiction causes exponential decay ([Zenodo](https://zenodo.org/records/19254667))
2. **Predicting Computational Cost from δ** — Same δ governs existence and discovery cost ([Zenodo](https://zenodo.org/records/18943573))
3. **Cognitive Sleep for LLMs** — Metabolic architecture prevents context rot, p<0.001 ([Zenodo](https://zenodo.org/records/19322371))

📦 All papers & data: [OSF Project](https://osf.io/mdh7b/) · 🔬 Formal proofs: [Lean 4](https://github.com/karesansui-u/delta-survival-papers/tree/main/lean) · 📄 18 patents filed

### Background

Software engineer based in Japan. Enterprise systems background, now focused on AI knowledge integrity research. ORCID: [0009-0008-1306-0316](https://orcid.org/0009-0008-1306-0316)
