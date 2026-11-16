# Fine-Tuning, Step by Step

Learn how four fine-tuning methods work, with small notebooks you can run on your own computer.
No previous knowledge of the methods or of the math behind them is needed.

## The task

All notebooks use one task, so the methods can be compared: a shop's search box.

`black sneakers under 50 dollars` → `FIND shoes color=BK max=50`

The command format and the color codes are the shop's own rules, so the model cannot guess them.
Every notebook follows the same 5 steps: load the model → write the examples → ask before training → train → ask after training.

| Notebook | Method | Learns from |
|---|---|---|
| `1_sft.ipynb` | SFT (Supervised Fine-Tuning) | 25 requests + correct commands |
| `2_dpo.ipynb` | DPO (Direct Preference Optimization) | 25 requests + a good and a bad command |
| `3_grpo.ipynb` | GRPO (Group Relative Policy Optimization) | 25 requests + a score function |
| `4_vision.ipynb` | Vision SFT | 24 tag pictures + correct commands |
| `5_measure.ipynb` | Measuring answers | how to score an answer |

All examples are written by hand in the notebooks, so they are easy to read and change.

## Requirements

- An NVIDIA GPU (the notebooks run on CUDA). They were written on a 16 GB GPU.
- Windows or Linux.
- [uv](https://docs.astral.sh/uv/), which installs Python 3.12 and all libraries.
- [VS Code](https://code.visualstudio.com/) with the Python and Jupyter extensions, or another notebook tool.

## Setup

```
git clone https://github.com/Mishagk/Case-Fine-Tuning.git
cd Case-Fine-Tuning
uv sync
```

Open the folder in VS Code, open `1_sft.ipynb`, choose the `.venv` kernel, and run the cells from top to bottom.
The first run downloads the model (about 1.7 GB).

## What is used

- **Model:** [`Qwen/Qwen3.5-0.8B`](https://huggingface.co/Qwen/Qwen3.5-0.8B), a small open model (Apache-2.0 license).
- **Libraries:** PyTorch, Hugging Face Transformers, TRL, PEFT and Datasets. The exact versions are in `uv.lock`.
- `pyproject.toml` only accepts library versions published before a fixed date, as a protection against new malicious uploads.
- Notebook 5, part 5 (optional) uses a local [Ollama](https://ollama.com/) model as a judge.
