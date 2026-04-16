### 矛盾はAIを壊す。問題は長さではなく、矛盾の蓄積です。

LLM は長い会話で劣化します。多くの場合はコンテキスト長の問題だと思われていますが、私の主張は少し違います。  
**本質は長さそのものではなく、未整理の矛盾の蓄積です。**

実験では、GPT-4o-mini は `100% → 10%`、Gemini は `100% → 0%` まで低下しました。  
1M トークン級の長大コンテキストでも、構造的な矛盾が入ると性能は大きく崩れます。一方で、矛盾を外部で整理すると精度は回復します。

この枠組みは、単なる比喩ではなく予測を出せる理論です。  
たとえば multi-attractor extension では、Gemini の精度が **`P = 1/(1+K/L)`** に従うと予測され、3点から導いた式が 5 つの文脈長（32K–512K）で **MAE 2%** で確認されました。  
つまり、**公理 → Lean 4 形式検証 → 予測 → 実験** の鎖を一応つないでいます。

---

### 🧬 実装

**[delta-prune](https://github.com/karesansui-u/delta-prune)** — LLM API に送る前に矛盾を検出・整理する軽量ミドルウェアです。3 行で使えます。 [![PyPI](https://img.shields.io/pypi/v/delta-prune)](https://pypi.org/project/delta-prune/)

```python
from delta_prune import DeltaPrune
prune = DeltaPrune(llm=OpenAILLM())
result = prune(messages)  # contradictions resolved
```

**[DeltaLint](https://github.com/karesansui-u/delta-lint)** — コードベース内の構造的矛盾を検出するスキャナです。モジュールの前提と実際の振る舞いが食い違う場所を見つけます。

---

### 特許関連

本研究に関連する構造維持機構については、日本で既に特許出願済みです。  
長期タスクを支える永続状態を土台としつつ、その上に構造持続方程式と矛盾解消原理に基づく整合性維持機構を重ねています。  
概要は [Patent Notice](https://github.com/karesansui-u/delta-survival-papers/blob/main/PATENTS.md) を参照してください。

---

### 📄 論文とデータ

> **「Context rot は長さの問題ではなく、矛盾の問題である。」**

| # | Paper | 要点 |
|---|-------|------|
| 1 | **Structural Collapse as Information Loss** | 構造持続方程式 `S = μ × e^{-δ}`。矛盾は指数的な崩壊として現れる。Multi-attractor prediction を確認。Lean 4 検証済み。 |
| 2 | **Predicting Computational Cost from δ** | 同じ `δ` が、解の存在だけでなく計算コストにも効く。感度指数はソルバー依存。 |
| 3 | **Contradiction Metabolism for LLMs** | 外部代謝により context rot を抑制。`+52.2pp`（n=3, p=0.027; 8-model sign test p=0.0107）。 |

📊 **[delta-survival-papers](https://github.com/karesansui-u/delta-survival-papers)** — 論文本文、TeX/PDF、11モデル・1000試行超の生データ、再現スクリプト、Lean 4 証明をまとめたリポジトリです。ダウンロード先は [DATA.md](https://github.com/karesansui-u/delta-survival-papers/blob/main/DATA.md) を参照してください。

🗂️ [Zenodo](https://zenodo.org/search?q=metadata.creators.person_or_org.name%3A%22Sunagawa%2C%20Akihito%22&l=list&p=1&s=10&sort=bestmatch) — 公開済みレコード一覧

📦 [OSF Project](https://osf.io/mdh7b/) — 論文・データ・コードの集約先

🔬 [Lean 4 formal proofs](https://github.com/karesansui-u/delta-survival-papers/tree/main/lean) — 160 propositions, `sorry = 0`, `axiom = 0`

---

Software engineer, Japan
