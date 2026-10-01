# The Seven Layers of AI, Layer 5: Generative AI

This notebook accompanies **Chapter 6, Layer 5: Generative AI** of the study guide *The Seven Layers of AI*. It contains every example program from the chapter in the order it appears, so you can run, change and experiment with the code as you read.

## What is in the notebook

For each program you will find:

1. **The explanation** from the guide that introduces the program.
2. **The code**, with a header explaining its purpose, how it works and what to look for, plus comments throughout.
3. **The output from a test run**, already saved in the notebook, so you can read it before running anything.
4. **The output shown in the guide**, for comparison. The two should match, apart from timings.
5. **What the output shows**, a short interpretation.
6. **Investigate** tasks, which suggest changes to make and questions to answer.

Run the `%%writefile l5_corpus.txt` cell first: several later programs read that file. `l5_mini_gpt.py` needs the autograd package and takes about a minute to train on a typical laptop.

## Programs

| # | File | Topic | Status |
|---|------|-------|--------|
| 1 | `l5_corpus.txt` | training text used by later programs | saves a data file |
| 2 | `l5_ngram.py` | an n-gram language model | runs in the notebook |
| 3 | `l5_bpe.py` | byte-pair encoding from scratch | runs in the notebook |
| 4 | `l5_embeddings.py` | embeddings from co-occurrence | runs in the notebook |
| 5 | `l5_mini_gpt.py` | a miniature GPT trained from scratch | runs in the notebook |
| 6 | `l5_sampling.py` | decoding strategies | runs in the notebook |
| 7 | `l5_rag.py` | the retrieval half of RAG | runs in the notebook |
| 8 | `l5_diffusion.py` | a diffusion model generating 2D data | runs in the notebook |
| 9 | `l5_llm_apis.py` | Using Real Generative Models | read only (see below) |

## Programs that are not run in the notebook

These programs need software, downloads or an API key that the notebook cannot assume you have. Their code is included so you can read it, and a note in the notebook marks each one. To run them yourself:

- **`l5_llm_apis.py`** needs the transformers and torch packages, an Anthropic API key and a local Ollama server. `pip install transformers torch anthropic requests`, set the `ANTHROPIC_API_KEY` environment variable, and install and start Ollama (https://ollama.com) for the local-model part. Each part can be run separately.

## Requirements

- Python 3.10 or later
- Jupyter (JupyterLab, Jupyter Notebook, or VS Code with the Jupyter extension)
- Packages: `numpy scikit-learn autograd`

The notebook takes about 2 minutes to run from top to bottom on a typical laptop.

## Setting up

These steps create a separate Python environment so the packages do not interfere with anything else on your computer. Run them in a terminal, from the folder that contains this README.

**Windows (PowerShell)**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
pip install jupyterlab numpy scikit-learn autograd
jupyter lab
```

**macOS or Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install jupyterlab numpy scikit-learn autograd
jupyter lab
```

JupyterLab opens in your browser. Double-click `Layer5_Generative_AI.ipynb` to open it.

**VS Code:** open this folder, open `Layer5_Generative_AI.ipynb`, and choose the `.venv` environment when VS Code asks you to select a kernel. Install the packages into that environment first, as above.

**Google Colab:** upload `Layer5_Generative_AI.ipynb` at https://colab.research.google.com. Most packages are already installed; if one is missing, remove the `#` from the `%pip install` line in the setup cell and run it.

## Using the notebook

1. **Run the setup cell first.** It is the first code cell. Uncomment the `%pip install` line if you have not installed the packages.
2. **Run cells from top to bottom** with Shift+Enter, or use *Run All*. Each program is self-contained, so after the setup cell you can also jump to any program and run just that one.
3. **Read the saved output before running.** It shows what to expect. When you run a cell, the saved output is replaced with yours.
4. **Compare with the guide.** The programs use fixed random seeds, so your numbers should match the guide exactly. Only timings, such as the seconds reported while training, vary between computers.
5. **Work through the Investigate tasks.** Edit the code directly in the cell and run it again. If you want to get back to the original, the code is also printed in the guide.
6. **Restart when things get confusing.** All programs share one Python session, so a variable changed in one cell can affect a later one. *Kernel > Restart Kernel and Clear Outputs* gives you a clean start.

## Troubleshooting

| Problem | What to do |
|---------|------------|
| `ModuleNotFoundError: No module named ...` | The package is not installed in the environment the notebook is using. Run `%pip install <package>` in a cell, then restart the kernel. |
| A cell has been running for a long time | Training programs can take a minute or more. Watch the `[*]` marker beside the cell; use *Kernel > Interrupt* to stop it. |
| Numbers differ slightly from the guide | Check you have not changed a seed or parameter. Very different package versions can also change results slightly; the notebooks were tested with NumPy 2.4, scikit-learn 1.8 and pandas 3.0. |
| `FileNotFoundError` for a data file | Run the cell that creates the file first (for example, the `%%writefile` cell), and keep the notebook in the folder it runs from. |

## Using this with learners

- Ask learners to **predict the output** before running a program, then explain any differences.
- Most Investigate tasks can be completed in 10 to 20 minutes and work well as paired activities.
- Encourage learners to **break the code deliberately** (change a learning rate, remove a line) and explain what happens. It is often the fastest way to understand why each line is there.

## Source

Programs and explanations are from *The Seven Layers of AI* study guide, Chapter 6. Citations in the code and text refer to the guide's reference list.

## License

The code in this repository (notebook code cells, scripts and `requirements.txt`) is released under the [MIT License](LICENSE).

The written content (explanations, exercises, Markdown files and study guide documents) is licensed under [CC BY-NC 4.0](LICENSE-CONTENT.md): you may share and adapt it for non-commercial use with credit, but not sell it or use it in paid courses or products.

Copyright © 2026 Trevor Smith.
