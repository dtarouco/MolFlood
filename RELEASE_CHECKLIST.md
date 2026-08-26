# MolFlood v1.0.0 Release Checklist

This checklist is intended to document the final verification steps for the first stable public release of MolFlood.

## 1. Notebook and core workflow

- [x] Full MolFlood pipeline executed successfully.
- [x] Held-out test set retained for final model evaluation.
- [x] Held-out test set is not used for algorithm selection.
- [x] Held-out test set is not used by Optuna for hyperparameter optimization.
- [x] Structural validation / group-aware cross-validation retained.
- [x] Applicability domain is calibrated from the training chemical space.
- [x] Applicability-domain classification annotates molecules rather than automatically removing them.
- [x] Applicability-domain diagnostics are available for the held-out test set.
- [x] External molecular prediction includes applicability-domain information.
- [x] External redocking / Compare Docking Predictions workflow removed from the core pipeline.
- [ ] Final notebook filename confirmed as `MolFlood_v1.0.0.ipynb`.
- [ ] Notebook header reports `Version: 1.0.0 — Stable`.
- [ ] All Public Beta / v0.9.x references that should not remain in the stable notebook have been removed.

## 2. Reproducibility

- [x] Pipeline functionality confirmed by the developers.
- [ ] Final release executed from a fresh local environment.
- [ ] Release dependencies installed from `requirements.txt`.
- [ ] Restart Kernel → Run All completed successfully.
- [ ] No manual modification of core pipeline cells was required during the final run.
- [ ] Random seeds and reproducibility settings are recorded.
- [ ] Dataset SHA-256 is generated/recorded when applicable.
- [ ] Model SHA-256 is generated/recorded when applicable.
- [ ] Environment/package metadata are generated/recorded.
- [ ] Model Card is generated/recorded.

## 3. Scientific validation

- [ ] Final held-out test metrics reviewed.
- [ ] RMSE reviewed.
- [ ] MAE reviewed.
- [ ] R² reviewed.
- [ ] Spearman correlation reviewed.
- [ ] Ranking diagnostics reviewed where applicable.
- [ ] Bootstrap analysis completed where enabled.
- [ ] Y-scrambling negative control completed where enabled.
- [ ] Applicability-domain threshold and test coverage reviewed.
- [ ] Predictions outside the applicability domain are clearly described as stronger structural extrapolations, not automatically invalid predictions.

## 4. Documentation

- [ ] `README.md` reports MolFlood v1.0.0 — Stable.
- [ ] `README.md` explains what a docking score is.
- [ ] `README.md` states that docking scores are not experimental binding affinities.
- [ ] `README.md` documents the local-first workflow.
- [ ] `README.md` describes rapid ML-assisted molecular prioritization.
- [ ] `README.md` highlights neglected and understudied diseases.
- [ ] `README.md` explains the applicability domain.
- [ ] `README.md` does not present external redocking as a required MolFlood step.
- [ ] `CITATION.cff` reports version `1.0.0`.
- [ ] `CHANGELOG.md` contains a `1.0.0` release entry.
- [ ] MIT License is present.

## 5. Tutorial

- [ ] Tutorial dataset added, if distributed with v1.0.0.
- [ ] Tutorial dataset provenance documented.
- [ ] Tutorial dataset redistribution/license status confirmed.
- [ ] Tutorial instructions checked.
- [ ] `tutorial/reference_results.md` completed using the official reference run.
- [ ] Tutorial reproduces the expected MolFlood workflow in a clean local environment.

## 6. GitHub release

- [ ] Final notebook committed to the repository.
- [ ] All v1.0.0 documentation changes committed.
- [ ] Local repository synchronized with GitHub.
- [ ] Repository is public.
- [ ] Final `main` branch inspected on GitHub.
- [ ] Tag `v1.0.0` created.
- [ ] GitHub Release titled `MolFlood v1.0.0` published.

## 7. Zenodo

- [ ] MolFlood repository enabled in the Zenodo GitHub integration.
- [ ] GitHub v1.0.0 release archived by Zenodo.
- [ ] Zenodo DOI generated.
- [ ] DOI added to `README.md`.
- [ ] DOI added to `CITATION.cff`.
- [ ] DOI and citation information verified.

## Release decision

MolFlood v1.0.0 should be considered released only after the final stable notebook and documentation are committed, the GitHub release is published, and the archived release can be cited persistently.
