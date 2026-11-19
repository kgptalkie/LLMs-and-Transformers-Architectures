# 11 Size, memory and the KV cache

`count-and-measure.ipynb` goes with lesson 11.8.

- The first three cells read Qwen3-8B's config and count its parameters. They run on any PC.
- From the fourth cell on, the notebook loads the full model on an NVIDIA GPU: a 15.3 GB download the first time,
  and about 18 GB of free GPU memory (15.3 GB of weights plus the KV cache at 8,192 tokens).

Install PyTorch with CUDA and `requirements.txt` first (main README, step 3).
