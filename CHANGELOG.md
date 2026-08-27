# Changelog

All notable changes to MolFlood are documented in this file.

## [Unreleased]

Changes under development for future MolFlood releases.

---

## [1.0.0] - 2026-08-27

### First stable release

MolFlood v1.0.0 is the first stable public release of the pipeline, following successful execution and validation of the complete workflow.

### Added

- User-focused notebook documentation explaining the main machine-learning analyses and validation outputs.
- Tutorial workflow with `tutorial_dataset.csv`.
- Example external-prediction dataset with `predict_dataset.csv`.
- Training-only algorithm selection and hyperparameter optimization.
- Group-aware structural cross-validation.
- Independent held-out test evaluation.
- DummyRegressor baseline comparison.
- Bootstrap confidence intervals for held-out performance metrics.
- Y-scrambling negative control.
- Tanimoto-based applicability-domain analysis.
- Empirical evaluation of prediction error inside and outside the applicability domain.
- Morgan fingerprint bit mapping to representative chemical environments.
- Global and local SHAP model interpretation.
- Reproducibility metadata, dataset hashes, environment records, and model checksums.
- Automatically generated Model Card.
- External docking-score prediction from trained MolFlood models.
- Local-first execution guidance.
- Flexible dependency installation for broader compatibility across local environments.

### Changed

- Docking score standardized as the predictive endpoint and terminology throughout the workflow.
- Final held-out test set is strictly isolated from algorithm selection and hyperparameter optimization.
- Applicability-domain status is treated as a structural-support annotation and does not remove molecules from held-out evaluation or external predictions.
- Documentation expanded for users without a machine-learning background.
- Plot titles, labels, notebook sections, and user-facing documentation standardized in English.
- Installation strategy changed from rigid dependency pinning to flexible runtime dependencies.
- Local execution is recommended for training and validating new target-specific models.
- Cloud execution remains possible, particularly for tutorials, workflow exploration, and prediction using previously trained models.

### Removed

- External redocking/reference-score evaluation from the main MolFlood workflow.
- Mandatory comparison between predicted docking scores and independently redocked molecules.

### Scientific scope

MolFlood predicts docking scores generated within a defined docking context. Predictions are intended for rapid molecular prioritization and should not be interpreted as experimental binding affinities, biological activities, or evidence of therapeutic efficacy.

The project places particular emphasis on supporting molecular-prioritization studies involving neglected and understudied diseases, including research environments with limited access to extensive computational infrastructure.

---

## [0.9.0] - 2026-08-24

### Public Beta

Initial public beta of MolFlood.

### Added

- Public Beta identity.
- Docking-score prediction workflow.
- Morgan + RDKit molecular representation.
- Structural split and GroupKFold validation.
- Training-only model selection and Optuna optimization.
- Dummy baseline.
- Bootstrap and Y-scrambling analyses.
- Applicability-domain analysis.
- SHAP interpretation.
- Reproducibility metadata and hashes.
- Model Card generation.
- External molecular prediction.
- External redocking/reference evaluation.
- Public-facing project metadata.
- MIT licensing.
