# MolFlood v1.0.0 Reference Run

This document records the reference execution used to verify MolFlood v1.0.0.

It is intended to provide users with a reproducibility reference for the official tutorial workflow. Values below should be completed from the actual release run rather than estimated or copied from a different dataset or MolFlood version.

## Release information

- **MolFlood version:** 1.0.0
- **Release status:** Stable
- **Execution mode:** Local Jupyter / JupyterLab
- **Full pipeline execution:** Passed

## Environment

- **Operating system:**
- **Python version:**
- **Environment type:** local
- **Dependencies installed from:** `requirements.txt`
- **Restart Kernel → Run All:** 
- **Unhandled exceptions:** 

## Tutorial dataset

- **Dataset name:**
- **Dataset source/provenance:**
- **Number of input molecules:**
- **Number of valid molecules used by MolFlood:**
- **Dataset SHA-256:**
- **Target:**
- **Disease / biological context:**
- **Docking software:**
- **Docking software version:**
- **Docking protocol identifier:**
- **Docking score name:** `docking_score`
- **Docking score units:**
- **Docking score direction:**

## Molecular representation

- **Primary structural representation:** Morgan fingerprints
- **Additional representation:** RDKit physicochemical descriptors
- **Morgan radius:**
- **Morgan fingerprint size:**

## Train / test validation

- **Split mode:**
- **Training molecules:**
- **Held-out test molecules:**
- **Test fraction:**
- **Random seed:**
- **Structural grouping method:**
- **Cross-validation method:**
- **Number of CV folds:**

The held-out test set must remain independent of algorithm selection and Optuna hyperparameter optimization.

## Selected model

- **Selected algorithm:**
- **Selection criterion:**
- **Best Optuna parameters:**
- **Number of Optuna trials:**
- **Model SHA-256:**

## Held-out test performance

The values in this section must refer to the complete held-out test set.

| Metric | Value |
|---|---:|
| RMSE | |
| MAE | |
| R² | |
| Spearman | |

The primary held-out metrics should not exclude molecules classified as outside the applicability domain.

## Applicability domain

- **Method:** Morgan fingerprint Tanimoto similarity
- **Reference chemical space:** training set
- **Threshold calibration:** training-derived
- **AD threshold:**
- **Held-out test molecules classified IN:**
- **Held-out test molecules classified OUT:**
- **Held-out test AD coverage:**

Applicability-domain classification is an annotation of structural support relative to the training chemical space. It does **not** automatically remove molecules from the held-out test set or from external prediction outputs.

### Optional held-out AD diagnostic

| Group | N | MAE | RMSE |
|---|---:|---:|---:|
| Overall held-out test | | | |
| AD IN | | | |
| AD OUT | | | |

If reported, these subgroup results are secondary diagnostics. The complete held-out test metrics remain the primary performance results.

## Additional validation

- **Bootstrap analysis completed:**
- **Y-scrambling completed:**
- **Ranking diagnostics completed:**
- **Morgan-bit interpretation completed:**
- **SHAP interpretation completed:**

## External molecular prediction check

- **External prediction workflow executed:**
- **Number of input molecules:**
- **Number of successfully predicted molecules:**
- **Applicability-domain annotation generated:**

External redocking or comparison against newly generated docking scores is **not required** for the MolFlood v1.0.0 core workflow.

## Generated reproducibility artifacts

- **Model artifact generated:**
- **Model Card generated:**
- **Dataset hash generated:**
- **Model hash generated:**
- **Environment metadata generated:**

## Reference-run conclusion

The reference run should be considered complete when the notebook executes from top to bottom in the documented local environment, produces the expected held-out evaluation and reproducibility artifacts, and completes external molecular prediction without requiring external redocking.
