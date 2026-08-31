# MolFlood

Machine Learning docking score prediction for neglected and understudied disease targets.

# Description

MolFlood is an open, reproducible machine-learning workflow designed for the prediction of molecular docking scores from extremely large molecule libraries at an outstanding speed, based on the molecular structure. Its emphasis is on therapeutic targets associated with **neglected and understudied diseases**.

The long-term goal is to provide support both for a reusable prediction pipeline and for a community-driven collection of validated, target-specific MolFlood models.

## Workflow overview

<p align="center">
  <img src="assets/molflood_pipeline_hq.png"
       width="950"
       alt="MolFlood machine-learning workflow">
</p>

## What is a docking score?

Molecular docking computationally evaluates possible binding poses of a small molecule (ligand) within a binding site of a molecular target. A **docking score** is the numerical value produced by the scoring function of the docking software to rank or evaluate these predicted poses.

In many commonly used docking protocols, more favorable docking scores are represented by lower (more negative) values. However, the numerical meaning, scale, and direction of the score depend on the docking software, scoring function, and protocol used.

A docking score should **not** be interpreted as an experimentally measured binding affinity. It is a computational score generated under a particular docking protocol and is primarily useful for comparing and prioritizing
molecules evaluated under compatible conditions.

MolFlood learns the relationship between molecular structure and docking scores previously generated for a specific target and docking protocol. It can then rapidly estimate docking scores for new molecules within that same modeling context.

## Why MolFlood?

Large-scale molecular docking campaigns can require substantial computational resources, particularly when very large molecular libraries need to be evaluated. This can represent an important limitation for research groups with restricted access to high-performance computing infrastructure.

MolFlood was designed to enable **very rapid ML-assisted screening of molecular libraries using previously trained and validated MolFlood models**. Once a target-specific model has been trained, new molecules can be prioritized at a fraction of the computational cost normally associated with performing a new docking calculation for every compound.

The goal is not to replace molecular docking or experimental validation. Instead, MolFlood is intended as a **molecular prioritization tool**: machine learning can rapidly screen large collections of molecules and help researchers identify subsets that deserve subsequent computational or experimental investigation.

This approach is particularly relevant to the broader mission of MolFlood: supporting research on **neglected and understudied diseases**, including research environments where access to extensive computational infrastructure may be limited.

As the MolFlood community grows, validated target-specific models may be shared through the project repository, allowing researchers to perform rapid local predictions without having to reproduce the original model-training process. Each model should remain associated with its target, docking protocol, validation results, applicability domain, and provenance metadata.

## Scientific scope

MolFlood predicts **docking scores generated under a documented computational docking context**.

A MolFlood prediction should not be interpreted as experimental binding affinity, IC50, Ki, Kd, direct biological activity, or therapeutic efficacy.

MolFlood models are target- and protocol-specific and should not be assumed to transfer to another biological target or incompatible docking protocol without retraining and validation.

## Current release

MolFlood v1.0.0

The workflow includes:

- Morgan fingerprints;
- RDKit physicochemical descriptors;
- structural train/test splitting;
- GroupKFold structural validation;
- training-only algorithm selection;
- Optuna hyperparameter optimization;
- DummyRegressor baseline;
- RMSE, MAE, R², and Spearman metrics;
- top-k/ranking evaluation;
- bootstrap analysis;
- Y-scrambling;
- Morgan/Tanimoto applicability domain;
- Morgan-bit interpretation;
- XAI techniques;
- dataset/model SHA-256 hashes;
- environment and dependency metadata;
- Model Card generation;
- external prediction;
- external evaluation against independent redocking/reference scores.

## Molecular representation

MolFlood uses Morgan fingerprints as the main structural representation and enriches them with RDKit physicochemical descriptors computed from SMILES.

Morgan fingerprints remain the default because they are strong, scalable, and widely used for QSAR-like tabular molecular modeling. Additional fingerprint families were intentionally removed from the current workflow to reduce dimensionality, noise, and unnecessary computational cost.

Future versions of MolFlood may incorporate and systematically evaluate additional molecular fingerprint representations, enabling broader comparisons of their impact on predictive performance, generalization, and computational efficiency.

## Installation

MolFlood is designed primarily as a **local-first workflow**. Training, validation, model interpretation, applicability-domain analysis, and molecular-library prediction can all be performed on the user's own computer, providing direct control over datasets, trained models, prediction results, and the computational environment.

Running MolFlood locally is particularly recommended when **training and validating new models**, as it provides greater control over the software environment, file persistence, computational resources, and reproducibility of long-running analyses such as hyperparameter optimization, cross-validation, bootstrap evaluation, and Y-scrambling.

### Local and cloud execution

MolFlood can also be executed in compatible **cloud-based Jupyter environments**. However, cloud execution is **not the recommended approach for training and validating new MolFlood models**, particularly when using free or temporary cloud sessions. Session time limits, disconnections, changing environments, resource restrictions, and non-persistent storage may interrupt computationally intensive analyses or make exact environment reproduction more difficult.

Cloud environments may still be convenient for **exploring the notebook, running the tutorial, or performing predictions with an already trained MolFlood model**, provided that the required dependencies and model files are available.

For the development and validation of new target-specific models, a dedicated local Python environment is therefore recommended.

### Recommended Python

```text
Python 3.12-3.14
```
## Training input

Minimum schema:

```csv
smiles,docking_score
CCO,-5.8
c1ccccc1,-6.4
```

The training dataset is expected to have been deduplicated before entering MolFlood.

## Basic workflow

1. Install dependencies.
2. Open the notebook in `notebooks/`.
3. Fill the **USER CONFIGURATION** cell.
4. Place `dataset.csv` in the configured project folder.
5. Restart the Python kernel.
6. Run the notebook from top to bottom.
7. Inspect validation, applicability domain, and interpretation outputs.
8. Use the saved model for external prediction.

## Community vision

MolFlood is intended to evolve into a community-driven resource for neglected and understudied disease research.

Researchers will be encouraged to train and validate target-specific MolFlood models and submit standardized model packages for review. Accepted models should include sufficient provenance, validation, applicability-domain information, software versioning, and redistribution metadata.

The formal MolFlood Community Model Standard will be defined separately.

## Citation

If you use MolFlood in scientific work, please cite the specific software version used.

### MolFlood v1.0.0

Tarouco, D., Pedebos, C. and Ligabue-Braun, R. (2026). *MolFlood: Docking Score Prediction Pipeline*. Zenodo. DOI: 10.5281/zenodo.22133992.

[![DOI](https://zenodo.org/badge/1345384712.svg)](https://doi.org/10.5281/zenodo.22133991)
