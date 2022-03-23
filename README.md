# Mjolnir

> *Mjolnir*: Thor's hammer, a divine instrument making its holder worthy of wielding lightning.

Cookiecutter template repository for managing machine learning research projects built with
[PyTorch-Lightning](https://pytorch-lightning.readthedocs.io/en/latest/), using [Hydra](https://hydra.cc/) for configuration,
[Anaconda](https://www.anaconda.com/) for python dependencies, and sane quality defaults (`black`, `isort`, `flake8`,
`precommit`).

Template created by ⚡️ Sidd Karamcheti ⚡️; if you find this useful, but are looking for my generic PyTorch setup,
definitely check out the [`kindling`](https://github.com/siddk/kindling) template!

---

## Setup

The preferred setup is via Github Templates (Green Button above --> "Use as Template") or upon new repository creation
(borrowed with gratitude from
[Stefan Buck's instructions](https://stefanbuck.com/blog/repository-templates-meets-github-actions)). Manually edit the
`cookiecutter.json` file (in browser!), then commit, and let Github Actions take care of the rest.

---

You can also load this repository via the default `cookiecutter` tool:

```bash
# Create a new directory with Cookiecutter templates (prompts you for config values)
cookiecutter gh:siddk/mjolnir

# If you've already initialized a github repo with same name, and want to replace contents (run from root of github repo)
cookiecutter gh:siddk/mjolnir -o ../ -f
```

## Cookiecutter Repository Structure

High-level overview of repository file-tree (expand on this as you build out your project). Feel free to restructure,
but this is what the template comes loaded with.

+ `conf` - Hydra structured configurations (`.py`) for various runs (used in lieu of `argparse` or `typed-argument-parser`)
+ `environments` - Serialized Conda Environments for both CPU and GPU (CUDA 11.0). Other architectures/CUDA toolkit
environments can be added here as necessary.
+ `src/` - Source Code - has all utilities for preprocessing, Lightning Model definitions, utilities.
    + `preprocessing/` - Preprocessing Code (fill in details for specific project).
    + `models/` - Lightning Modules (fill in details for specific project).
+ `tests/` - Tests - Please test your code... just, please (more details to come).
+ `train.py` - Top-Level (main) entry point to repository, for training and evaluating models. Can define additional
top-level scripts as necessary.
+ `Makefile` - Top-level Makefile (by default, supports `conda` serialization, and linting). Expand to your needs.
+ `.flake8` - Flake8 Configuration File (Sane Defaults).
+ `.pre-commit-config.yaml` - Pre-Commit Configuration File (Sane Defaults).
+ `pyproject.toml` - Black and isort Configuration File (Sane Defaults).
+ `ARCHITECTURE.md` - Write up of repository architecture/design choices, how to extend and re-work for different
applications.
+ `CONTRIBUTING.md` - Detailed instructions for contributing to the repository, in furtherance of the default
instructions above.
+ `README.md` - Details for setting up / loading serialized Conda environments & intro to the repo.
+ `LICENSE` - By default, research code is made available under the GPLv3 License. Change as you see fit, but think
deeply about why!
