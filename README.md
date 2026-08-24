<p align="center">
  <img src="assets/molflood_logo.png" width="280" alt="MolFlood logo">
</p>

# MolFlood

**Docking Score Prediction Pipeline**

**Version:** 0.9.0 — Public Beta

**Developed by:** Davidt Tarouco, Dr. Conrado Pedebos, and Dr. Rodrigo Ligabue-Braun

MolFlood is an open, reproducible machine-learning workflow for predicting molecular docking scores from molecular structure, with particular emphasis on therapeutic targets associated with **neglected and understudied diseases**.

The long-term goal is to support both a reusable prediction pipeline and a community-driven collection of validated, target-specific MolFlood models.

## Workflow overview

<p align="center">
  <img src="assets/molflood_minipipeline.png"
       width="650"
       alt="MolFlood machine-learning workflow">
</p>

## Scientific scope

MolFlood predicts **docking scores generated under a documented computational docking context**.

A MolFlood prediction should not be interpreted as experimental binding affinity, IC50, Ki, Kd, direct biological activity, or therapeutic efficacy.

MolFlood models are target- and protocol-specific and should not be assumed to transfer to another biological target or incompatible docking protocol without retraining and validation.

## Current release

MolFlood v0.9.0 is a **Public Beta**.

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

Recommended Python:

```text
Python 3.12-3.14
```

Install dependencies:

```bash
python -m pip install -r requirements.txt
```

## Repository structure

```text
MolFlood/
├── README.md
├── LICENSE
├── CITATION.cff
├── CHANGELOG.md
├── CONTRIBUTING.md
├── CODE_OF_CONDUCT.md
├── SECURITY.md
├── requirements.txt
├── notebooks/
├── tutorial/
├── assets/
├── docs/
├── community_models/
└── .github/
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
9. If independent redocking/reference scores become available, evaluate them in the notebook.

## Tutorial dataset

A developer-provided tutorial dataset is planned for the public release workflow so users can verify their environment and learn the outputs before applying MolFlood to their own docking campaigns.

## Applicability domain

External predictions include Morgan/Tanimoto-based applicability-domain information such as:

```text
docking_score_predicted
max_tanimoto_to_training
within_applicability_domain
```

Outside-domain predictions represent stronger chemical extrapolation and should be interpreted with additional caution.

## Community vision

MolFlood is intended to evolve into a community-driven resource for neglected and understudied disease research.

Researchers will be encouraged to train and validate target-specific MolFlood models and submit standardized model packages for review. Accepted models should include sufficient provenance, validation, applicability-domain information, software versioning, and redistribution metadata.

The formal MolFlood Community Model Standard will be defined separately.

## Security

MolFlood currently serializes trained Python models with Joblib.

**Do not load an unreviewed `.joblib` artifact from an untrusted source in a trusted environment.**

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md).

## Citation

Citation metadata are provided in `CITATION.cff`.

Users should cite the **specific MolFlood version** used in a scientific analysis. A DOI can be added after an archived Zenodo release is created.

## License

MolFlood source code is released under the **MIT License**.

See [LICENSE](LICENSE).

## Authors

- Davidt Tarouco
- Dr. Conrado Pedebos
- Dr. Rodrigo Ligabue-Braun

## Release status

MolFlood v0.9.0 is a **Public Beta**. The stable v1.0.0 release is intended to follow complete validation in a clean environment using the official tutorial workflow.
