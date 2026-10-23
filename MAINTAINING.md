# Maintaining this repository

Notes for the authors: how to publish the repository, archive it on Zenodo, and keep the code, the expected outputs, the notebooks and the book in step.

## Publishing it for the first time

The folder you downloaded is already a git repository with one commit, so it only needs a home on GitHub.

### 1. Put it on GitHub

**With GitHub Desktop** (no command line): install [GitHub Desktop](https://desktop.github.com/) and sign in. Choose **File → Add local repository**, select this folder, then click **Publish repository**. Keep the name `deep-learning-with-python-code`, untick **Keep this code private**, and click **Publish repository**.

**With the command line:** on github.com, click **+ → New repository**, name it `deep-learning-with-python-code`, make it **Public**, and leave every "Initialize this repository" option unticked (the README, license and `.gitignore` are already here). Then, in this folder:

```bash
git remote add origin https://github.com/YOUR-ACCOUNT/deep-learning-with-python-code.git
git push -u origin main
```

### 2. Connect the repository to Zenodo

1. Go to [zenodo.org](https://zenodo.org/) and log in with **Log in with GitHub** (or link GitHub to an existing account in its settings).
2. Open the profile menu, choose **GitHub**, and click **Sync now**.
3. Find `deep-learning-with-python-code` in the list and switch it **On**.

From now on, every GitHub release of the repository is archived on Zenodo automatically, with its own DOI. Zenodo takes the title, authors, license, keywords and description from [`CITATION.cff`](CITATION.cff), so check that file first. The ORCID iDs and affiliations of the other two authors can be added there in the same form as Viraj Gulhane's.

### 3. Make the first release

On the repository's GitHub page, click **Releases → Create a new release**. Under **Choose a tag**, type `v1.0.0` and choose **Create new tag**, give the release a title such as *Version 1.0.0 — first edition*, and click **Publish release**. Zenodo usually archives a small repository like this one within a few minutes; the new record then appears under **GitHub** in your Zenodo account.

### 4. Put the DOI in the book

The Zenodo record shows two kinds of DOI: one for this exact version, and a **concept DOI** that always resolves to the latest version (under *Versions*, "Cite all versions? You can cite all versions by using the DOI …"). Use the concept DOI in the book, so that its link stays correct after later releases.

The book prints the repository's two addresses from two lines near the top of `book.tex`:

```latex
\urldef{\coderepodoi}\url{https://doi.org/10.5281/zenodo.XXXXXXX}
\urldef{\coderepogithub}\url{https://github.com/YOUR-ACCOUNT/deep-learning-with-python-code}
```

Replace `XXXXXXX` with the number at the end of the concept DOI and `YOUR-ACCOUNT` with the GitHub account, then compile the book again (`pdflatex book.tex`, three times).

### 5. Optional: add the DOI to this repository

The Zenodo record page offers a DOI badge (click the DOI badge on the record to copy its Markdown); paste it under the title of [`README.md`](README.md). You can also add a line `doi: 10.5281/zenodo.NNNNNNN` (the concept DOI) to `CITATION.cff`, so that GitHub's **Cite this repository** button includes it. Commit the change and make a release `v1.0.1`; the concept DOI stays the same.

## Changing a program

1. Edit the `.py` file in its chapter folder, and the matching listing in the book.
2. Run `python tools/check_outputs.py chapter-NN-.../chNN_programM.py --update` to rewrite its expected output from a fresh run, then update the book's printed output to match.
3. Run `python tools/make_notebooks.py`, so that the chapter's notebook holds the new code and output.
4. Run `python tools/check_outputs.py chapter-NN-...` to confirm the whole chapter still matches.
5. Commit, raise `version` in `CITATION.cff`, and make a new GitHub release (`v1.0.1`, `v1.1.0`, …). Zenodo archives it under the same concept DOI.

To add a new program, also add an entry for it to [`tools/programs.json`](tools/programs.json) and a row to its chapter's `README.md`.

## The tools

| Script | What it does |
|:--|:--|
| [`tools/check_outputs.py`](tools/check_outputs.py) | runs programs from their folders and compares their output with `expected_output/` (`--diff` shows differences, `--update` rewrites the expected output) |
| [`tools/make_notebooks.py`](tools/make_notebooks.py) | rebuilds every chapter's notebook from the `.py` files and expected outputs (`--check` only reports notebooks that are out of date) |
| [`tools/count_idioms.py`](tools/count_idioms.py) | recomputes the idiom counts in the tables of Appendices A–C |
| [`tools/programs.json`](tools/programs.json) | the index the other tools read: each program's chapter, number, file, title, book section and runtime, and the reason its output varies, if it does |
