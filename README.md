# LLMs and Transformers: Architecture, Theory and Interviews

Notebooks and course files for **LLMs and Transformers: Architecture, Theory and Interviews**, a KGP Talkie course.

The course explains how large language models work, from words as numbers through RNNs, attention and the full
Transformer, to BERT, GPT and T5, scaling laws, instruction tuning, the modern transformer block, Mixture of Experts,
memory and the KV cache, quantization, reasoning models, benchmarks and real model teardowns. Most lessons are
explained with animated scenes. The three notebook lessons below let you check the ideas on a real model yourself.

Every folder matches a course section by its number, and each has a short README that says what you need before you
run its notebook.

## The notebooks

| Lesson | Notebook | What you do | Hardware |
|---|---|---|---|
| 2.8 Tokenize real text in a notebook | `02 Words as numbers/tokenize-real-text.ipynb` | Turn real text into GPT-2 token ids, then compare how numbers, code, French and Hindi split | Any PC, no GPU |
| 11.8 Count and measure in a notebook | `11 Size, memory and the KV cache/count-and-measure.ipynb` | Count Qwen3-8B's parameters from its config, load it, measure its GPU memory and watch the KV cache grow | NVIDIA GPU with about 18 GB free |
| 12.7 16 bit vs 4 bit, measured | `12 Quantization/16-bit-vs-4-bit.ipynb` | Load Qwen3-8B in 16 bit and in 4 bit, then compare memory and answers | NVIDIA GPU with about 17 GB free (the 4-bit part alone needs about 6 GB) |

Qwen3-8B is a 15.3 GB download from Hugging Face the first time you load it. GPT-2's tokenizer is about 3 MB.

## 1. Install the tools

| What | Where to get it |
|---|---|
| Python 3.13 (the lessons use 3.13; 3.12 also works) | [python.org/downloads](https://www.python.org/downloads/) |
| Visual Studio Code | [code.visualstudio.com/download](https://code.visualstudio.com/download) |
| The Python and Jupyter extensions for VS Code | Search "Python" and "Jupyter" (both by Microsoft) in the VS Code Extensions view |
| For 11.8 and 12.7 only: an NVIDIA driver | [nvidia.com/drivers](https://www.nvidia.com/en-us/drivers/) |

## 2. Get these files

Click the green **Code** button on this page, then **Download ZIP**, and unzip it anywhere you like. If you use Git:

```bash
git clone https://github.com/kgptalkie/LLMs-and-Transformers-Architectures.git
```

In VS Code, use **File > Open Folder** and open the whole `LLMs-and-Transformers-Architectures` folder, so every section is in the
Explorer.

## 3. Create the environment

Open a terminal in the `LLMs-and-Transformers-Architectures` folder (in VS Code: **Terminal > New Terminal**) and run:

```bash
python -m venv .venv
```

Activate it. On Windows:

```bash
.venv\Scripts\activate
```

On macOS or Linux:

```bash
source .venv/bin/activate
```

For lesson 2.8 alone, that is enough: its first cell installs `transformers` for you.

For 11.8 and 12.7, install PyTorch with CUDA first. Pick your system on [pytorch.org/get-started](https://pytorch.org/get-started/locally/)
and run the command it shows. Then install the rest:

```bash
pip install -r requirements.txt
```

Open a notebook, click **Select Kernel** at the top right, and choose the `.venv` environment.

## Sections

| # | Section | Files |
|---|---|---|
| 02 | Words as numbers | `tokenize-real-text.ipynb` |
| 11 | Size, memory and the KV cache | `count-and-measure.ipynb` |
| 12 | Quantization | `16-bit-vs-4-bit.ipynb` |

The notebooks have no saved outputs, so what you see is what you ran. Your numbers for memory can differ a little
from the lessons with a different GPU, driver or library version. The counts (parameters, token ids, KV cache size)
come out the same.
