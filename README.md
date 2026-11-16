Learn how four fine-tuning methods work as personal learning and understanding of novel approaches.

---

IMPORTANT: The main purpose is only personal learning and training in the field of computer vision, not a commercial or industry real purposes.

----

| Notebook | Method | Learns from |
|---|---|---|
| `1_sft.ipynb` | SFT (Supervised Fine-Tuning) | 25 requests + correct commands |
| `2_dpo.ipynb` | DPO (Direct Preference Optimization) | 25 requests + a good and a bad command |
| `3_grpo.ipynb` | GRPO (Group Relative Policy Optimization) | 25 requests + a score function |
| `4_vision.ipynb` | Vision SFT | 24 tag pictures + correct commands |
| `5_measure.ipynb` | Measuring answers | how to score an answer |

## What is used
- **Model:** [`Qwen/Qwen3.5-0.8B`](https://huggingface.co/Qwen/Qwen3.5-0.8B)
- **Libraries:** PyTorch, Hugging Face Transformers, TRL, PEFT and Datasets. The exact versions are in `uv.lock`.
