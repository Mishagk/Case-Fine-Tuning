# Fine-tuning, step by step

All notebooks use one task, so the methods can be compared: a shop's search box.

`black sneakers, under 50 dollars, newest first` → `FIND shoes color=BK max=50 sort=new`

The command format, the color codes and the synonyms are house rules the model cannot know.
Each notebook compares **A. prompting only** (every rule in a long prompt) with **B. training**.

| Notebook | Method | Starts from | Learns from |
|---|---|---|---|
| `1_sft.ipynb` | SFT | a short prompt | 260 requests + correct commands |
| `2_dpo.ipynb` | DPO | the long prompt | 260 pairs: correct vs typical mistake |
| `3_grpo.ipynb` | GRPO | the long prompt | 260 requests + a scoring function |
| `4_vision.ipynb` | Vision SFT | a short prompt | 240 tag pictures + correct commands |
| `5_measure.ipynb` | Measuring | | how to score answers |

Notebooks 1–3 use the same 300 examples and the same 40 test requests, so their accuracy can be compared directly.

Model: `Qwen/Qwen3.5-0.8B` (small, open, Apache-2.0). It downloads once, on first use.

## Setup (once)
1. Run `uv sync` in this folder.
2. Open a notebook in VS Code. It uses this folder's `.venv` automatically.
