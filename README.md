# Deep Learning with Python — Code for Every Chapter

Companion code for the book **_Deep Learning with Python: A Practical and Mathematical Introduction_** by **Nitin Rakesh, Viraj Gulhane and Shreyas Hole** (first edition, 2026).

Every program printed in the book is here, chapter by chapter, under the file name the book gives it: Chapter 9's Program 3 is [`chapter-09-forward-propagation-and-multilayer-networks/ch09_program3.py`](chapter-09-forward-propagation-and-multilayer-networks/ch09_program3.py). Each program is a complete script that runs on its own, on an ordinary computer with no GPU, and none of them downloads anything: every dataset they use ships with scikit-learn or Matplotlib.

In total: 136 numbered programs across the 28 chapters (all of them Python except Chapter 2's install script), the traceback example `broken.py`, and one companion file for each of Appendices A–D — 140 Python files in all.

## What each chapter folder contains

| Item | What it is |
|:--|:--|
| `README.md` | the chapter's programs: number, book section, what each one does, and how long it takes to run |
| `chNN_programM.py` | the programs themselves, identical to the listings printed in the book |
| `expected_output/` | the complete output of every program, exactly as printed in the book |
| `chNN_notebook.ipynb` | every program of the chapter in one notebook, for Jupyter or Google Colab |

## Quick start

1. Install Python 3.10 or newer from [python.org](https://www.python.org/downloads/) (tick *Add Python to PATH* on Windows).
2. Download this repository with the green **Code** button → **Download ZIP**, and unzip it (or clone it with git, using the address under the same button).
3. Open a terminal in the unzipped folder, then create an environment and install the libraries:

   ```bash
   python3 -m venv dlbook              # Windows: python -m venv dlbook
   source dlbook/bin/activate          # Windows: dlbook\Scripts\activate
   python -m pip install -r requirements.txt
   ```

   If Windows PowerShell refuses to run the activation script, use the Command Prompt instead, or run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` once in PowerShell.

4. Run a program from inside its chapter folder, and compare what it prints with its expected output:

   ```bash
   cd chapter-01-what-is-deep-learning
   python ch01_program1.py
   ```

   The output should match [`expected_output/ch01_program1.txt`](chapter-01-what-is-deep-learning/expected_output/ch01_program1.txt).

Chapter 2 of the book explains each of these steps. On Linux, `python -m pip install torch --index-url https://download.pytorch.org/whl/cpu` installs a much smaller, CPU-only PyTorch; no program in the book needs a GPU. TensorFlow is needed only by Chapter 13's Program 3 and Appendix D; install it with `python -m pip install -r requirements-tensorflow.txt`.

## Running in Google Colab (nothing to install)

1. Go to [colab.research.google.com](https://colab.research.google.com/) and choose **File → Open notebook → GitHub**.
2. Paste the address of this repository's GitHub page, press Enter, and pick a chapter's notebook, for example `chapter-09-forward-propagation-and-multilayer-networks/ch09_notebook.ipynb`.
3. Run the cells from top to bottom (**Runtime → Run all**).

Each program takes two cells: the first writes the program to a file (change it there to experiment), the second runs it as a script, exactly as in the book. Its expected output follows, so you can compare. Everything the programs need is already installed on Colab, except for a few libraries used in Chapter 28, which that chapter's notebook installs in its first cell.

## Chapters

| Chapter | Title | Programs | Time to run all |
|--:|:--|--:|--:|
| 1 | [What Is Deep Learning?](chapter-01-what-is-deep-learning/) | 1 | < 1 s |
| 2 | [Setting Up Python for Deep Learning](chapter-02-setting-up-python-for-deep-learning/) | 4 | 8 s |
| 3 | [Vectors, Matrices, and Tensors](chapter-03-vectors-matrices-and-tensors/) | 4 | 3 s |
| 4 | [Derivatives, Gradients, and the Chain Rule](chapter-04-derivatives-gradients-and-the-chain-rule/) | 5 | 1 s |
| 5 | [The Artificial Neuron](chapter-05-the-artificial-neuron/) | 4 | 2 s |
| 6 | [The Perceptron](chapter-06-the-perceptron/) | 3 | < 1 s |
| 7 | [Activation Functions](chapter-07-activation-functions/) | 4 | < 1 s |
| 8 | [Loss Functions](chapter-08-loss-functions/) | 4 | < 1 s |
| 9 | [Forward Propagation and Multilayer Networks](chapter-09-forward-propagation-and-multilayer-networks/) | 4 | 1 s |
| 10 | [Backpropagation](chapter-10-backpropagation/) | 6 | 2 s |
| 11 | [Gradient Descent and Optimizers](chapter-11-gradient-descent-and-optimizers/) | 4 | < 1 s |
| 12 | [Regularization and Generalization](chapter-12-regularization-and-generalization/) | 7 | 17 s |
| 13 | [Building Networks with PyTorch and Keras](chapter-13-building-networks-with-pytorch-and-keras/) | 5 | 1 min |
| 14 | [Convolution and CNN Fundamentals](chapter-14-convolution-and-cnn-fundamentals/) | 6 | 18 s |
| 15 | [CNN Architectures and Transfer Learning](chapter-15-cnn-architectures-and-transfer-learning/) | 4 | 22 s |
| 16 | [Recurrent Neural Networks](chapter-16-recurrent-neural-networks/) | 5 | 23 s |
| 17 | [LSTM and GRU](chapter-17-lstm-and-gru/) | 5 | 5 min |
| 18 | [Attention Mechanisms](chapter-18-attention-mechanisms/) | 4 | 33 s |
| 19 | [Transformers](chapter-19-transformers/) | 4 | 37 s |
| 20 | [Deep Learning for NLP](chapter-20-deep-learning-for-nlp/) | 5 | 27 s |
| 21 | [Autoencoders and Variational Autoencoders](chapter-21-autoencoders-and-variational-autoencoders/) | 5 | 35 s |
| 22 | [Generative Adversarial Networks](chapter-22-generative-adversarial-networks/) | 5 | 1 min |
| 23 | [Diffusion Models](chapter-23-diffusion-models/) | 3 | 2 min |
| 24 | [Object Detection](chapter-24-object-detection/) | 6 | 13 min |
| 25 | [Image Segmentation](chapter-25-image-segmentation/) | 6 | 15 min |
| 26 | [Deep Learning for Time Series](chapter-26-deep-learning-for-time-series/) | 8 | 4 min |
| 27 | [Explainability and Responsible AI](chapter-27-explainability-and-responsible-ai/) | 8 | 2 min |
| 28 | [Deploying Deep Learning Models](chapter-28-deploying-deep-learning-models/) | 7 | 4 min |

## Appendices

| Appendix | Title | Listings | Time to run |
|:-:|:--|--:|--:|
| A | [Python Refresher](appendix-a-python-refresher/) | 17 | 2 s |
| B | [NumPy Reference](appendix-b-numpy-reference/) | 12 | < 1 s |
| C | [PyTorch Reference](appendix-c-pytorch-reference/) | 10 | 3 s |
| D | [TensorFlow/Keras Reference](appendix-d-tensorflow-keras-reference/) | 7 | 9 s |

Appendix E, the Formula Sheet, has no code.

Times were measured on a 2-core CPU without a GPU; all 140 files together take about 51 minutes. Most programs finish in seconds, while a few in the later chapters train networks for several minutes.

## Checking your results automatically

[`tools/check_outputs.py`](tools/check_outputs.py) runs programs and compares what each one prints with its expected output:

```bash
python tools/check_outputs.py chapter-05-the-artificial-neuron                 # one chapter
python tools/check_outputs.py chapter-05-the-artificial-neuron/ch05_program2.py # one program
python tools/check_outputs.py                                                   # everything
```

Each program is reported as `MATCH` (identical), `CLOSE` (the same apart from small differences in the last digits, which other library versions or processors can produce), `DIFFERENT` or `ERROR`. A few outputs cannot match the book exactly, by design, and the checker labels them:

- Chapter 2, Program 2 (`ch02_program2.py`): prints the library versions installed on your computer.
- Chapter 2, Program 4 (`ch02_program4.py`): its first two runs are deliberately unseeded, so they change every time.
- Chapter 2's traceback example (`broken.py`): your traceback shows the full path to the file.
- Chapter 10, Program 5 (`ch10_program5.py`): it measures time on your computer.
- Chapter 17, Program 4 (`ch17_program4.py`): it measures time on your computer.
- Chapter 28, Program 1 (`ch28_program1.py`): its TorchScript file records the program's location on disk, so that file's size depends on the folder you run it from.
- Chapter 28, Program 2 (`ch28_program2.py`): it measures time on your computer.
- Chapter 28, Program 3 (`ch28_program3.py`): it measures time on your computer.

## Software versions

Every expected output was checked by running the programs with the versions below. Other versions should run the programs too, but training runs may then print slightly different numbers; `tools/check_outputs.py` reports differences of under 1% as `CLOSE`.

| Library | Version |
|:--|:--|
| Python | 3.11.15 |
| NumPy | 2.4.4 |
| SciPy | 1.17.1 |
| pandas | 3.0.2 |
| Matplotlib | 3.10.9 |
| scikit-learn | 1.8.0 |
| PyTorch | 2.14.0, run on a CPU |
| TensorFlow / Keras | 2.21.0 / 3.15.1 |
| ONNX / ONNX Runtime | 1.23.1 / 1.25.0 |
| Flask / Requests | 3.1.3 / 2.33.1 |

## Figures

[`figure-scripts/`](figure-scripts/) holds the scripts that draw the book's figures, so that no figure is a picture of a result you cannot reproduce yourself. See its [README](figure-scripts/README.md).

## How to cite

If this code helps your teaching or research, please cite the book:

> Nitin Rakesh, Viraj Gulhane and Shreyas Hole. *Deep Learning with Python: A Practical and Mathematical Introduction*. First edition, 2026.

To cite the code itself, use the **Cite this repository** button on this repository's GitHub page, which gives a ready-made APA or BibTeX entry from [`CITATION.cff`](CITATION.cff); every release is archived on Zenodo with its own DOI.

## License

The code in this repository is released under the [MIT License](LICENSE): you may use, change and share it, in teaching or anywhere else, provided the copyright notice is kept. The book itself is not part of this repository and remains © 2026 the authors, all rights reserved.

## Authors

Nitin Rakesh, Viraj Gulhane and Shreyas Hole. Found a problem in a program, or a difference from the book that this README does not explain? Please open an issue on GitHub.
