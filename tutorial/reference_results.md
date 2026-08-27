# MolFlood v1.0.0 Reference Run

This document records the reference execution used to verify MolFlood v1.0.0.

It is intended to provide users with a reproducibility reference for the official tutorial workflow. Values below should be completed from the actual release run rather than estimated or copied from a different dataset or MolFlood version.

## Release information

- **MolFlood version:** 1.0.0
- **Release status:** Stable
- **Execution mode:** Local Jupyter / JupyterLab
- **Full pipeline execution:** Passed

## Tutorial dataset

- **Dataset name:** `tutorial_dataset.csv`
- **Number of input molecules:** 100k
- **Number of valid molecules used by MolFlood:** 100k
- **Target:** Nipah Virus RNA polymerase L
- **Disease / biological context:** Nipah Virus
- **Docking software:** Unidock
- **Docking software version:** 1.2.0
- **Docking score name:** `docking_score`

## Molecular representation

- **Primary structural representation:** Morgan fingerprints
- **Additional representation:** RDKit physicochemical descriptors
- **Morgan radius:** 2
- **Morgan fingerprint size:** 2048

## Train / test validation

- **Split mode:** Random Stratified
- **Training molecules:** 80k
- **Held-out test molecules:** 20k
- - **Number of Optuna trials:** 75

The held-out test set must remain independent of algorithm selection and Optuna hyperparameter optimization.
