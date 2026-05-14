# Bayesian Statistics — Introductory Course

An undergraduate introduction to Bayesian statistics covering probability foundations, generative modeling, Bayesian inference, conjugate models, MCMC, hierarchical models, and Bayesian regression. Translated from a Spanish course originally given to undergraduates.

## Setup

```
pip install -r requirements.txt
jupyter notebook
```

The notebooks require `pymc` v5 or later. The original Spanish course used `pymc3`, which is no longer maintained — the imports in this version have been migrated.

## Structure

```
├── Slides/      — Lecture slide decks (PowerPoint)
├── Notebooks/   — Hands-on Jupyter notebooks
└── Data/        — Datasets used by the notebooks
```

## Slides

Roughly in lecture order:

| # | Deck | Topic |
|---|---|---|
| 0 | `Slides/0. Course Introduction - Bayesian.pptx` | Course overview, frequentist review, motivation for Bayesian |
| 1 | `Slides/1. Probability - Intro.pptx` | Probability foundations, random variables, conditional probability, Bayes' theorem |
| 2 | `Slides/2. Probability - Distributions.pptx` | Discrete and continuous probability distributions, parametric families |
| 3 | `Slides/3. Probability - Data Generation.pptx` | Generative models, urn examples, prior distributions |
| 4 | `Slides/4. Bayesian Inference.pptx` | Bayes' theorem applied, conjugate models, Bayes factor |

## Notebooks

Sequence recommended for the course (numbered first, then thematic):

| Notebook | What it covers |
|---|---|
| `Notebooks/1. Coin - Frequentist.ipynb` | Frequentist intro using the coin example — confidence intervals via the binomial |
| `Notebooks/2. Probability_Functions.ipynb` | Discrete distributions: Bernoulli, Binomial, Geometric, Negative Binomial; expected value and variance |
| `Notebooks/3. Generative Model - Simulation.ipynb` | Simulating generative models (urns, normal-normal); prior-induced uncertainty |
| `Notebooks/Continuous Probability Distributions.ipynb` | PDF vs CDF, proportionality, normalization constant for the Normal |
| `Notebooks/Bayesian Inference.ipynb` | Urn model, Beta-Binomial conjugate updating, posterior predictive, utility |
| `Notebooks/Monster Example.ipynb` | Gamma-Gamma conjugate model applied to the MONSTER dataset (heart rate pre/post drink) |
| `Notebooks/Bayes_Factor.ipynb` | Bayes factor for hypothesis testing via the posterior predictive |
| `Notebooks/Gibbs Beta-Binomial.ipynb` | Hand-coded Gibbs sampler for a Beta-Binomial model with unknown n |
| `Notebooks/MCMC.ipynb` | Monte Carlo integration, Markov chains, Gibbs sampling on a bivariate normal |
| `Notebooks/Regression.ipynb` | Bayesian linear regression with PyMC |
| `Notebooks/Leukemia.ipynb` | Hierarchical Exponential model and Bayesian linear model on a leukemia survival dataset |
| `Notebooks/Hierarchical Models.ipynb` | Pooled vs unpooled vs partial-pooling Beta-Binomial models with PyMC |

## Data

- `Data/MONSTER.csv` — Pre/post heart-rate experiment (3 groups: drink, control, placebo). Column headers: `SEX, AGE, GROUP, CL, FI, PID, OE, HR_PRE, HR_POST` (translated from the original `SEXO, EDAD, GRUPOS, …, FCPRE, FCPOST`).
- `Data/res_demo_1.csv` — Small synthetic dataset used by the Regression notebook.
- Note: `Leukemia.ipynb` expects a separate `Leukemia.csv` (R `Stat2Data` package — see link inside the notebook).

## Notes on the translation

- Notebooks have been translated cell-by-cell: markdown text, plot labels, and code comments are in English. Code logic is unchanged.
- Cell outputs were stripped — re-run notebooks to regenerate them.
- A few near-duplicate notebooks in the original (`Inferencia Bayesiana(1).ipynb`, `3. Modelo generador - Simulación(1).ipynb`) were not ported separately, as they differ only in minor edits from the main versions.
- Slide images, equations, and any text embedded in images remain in their original form. Body text and bullet points have been translated.
- `pymc3` calls were migrated to modern `pymc` (v5); see `requirements.txt`.
