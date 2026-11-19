# 12 Quantization

`16-bit-vs-4-bit.ipynb` goes with lesson 12.7. It loads Qwen3-8B twice on an NVIDIA GPU, first in 16 bit (about
15.3 GB), then in 4 bit with bitsandbytes (about 5.7 GB).

- The model is a 15.3 GB download the first time; the 4-bit load reuses the same files.
- Run the cell that deletes the 16-bit model before the 4-bit load, so both never sit in memory at once.
- With less than about 17 GB of free GPU memory, skip the 16-bit cells and run only the 4-bit part.

Install PyTorch with CUDA and `requirements.txt` first (main README, step 3).
