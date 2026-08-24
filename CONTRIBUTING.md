# Contributing to MolFlood

MolFlood welcomes contributions that improve reproducibility, documentation, usability, validation methodology, neglected-disease support, and future community-model infrastructure.

## Before opening a pull request

Please:

1. keep changes focused;
2. explain the scientific or usability motivation;
3. avoid changing validation methodology silently;
4. document new dependencies;
5. update documentation when behavior changes;
6. confirm clean-kernel execution when relevant.

## Scientific-method changes

Changes affecting splitting, cross-validation, features, model selection, hyperparameter optimization, applicability domain, uncertainty, external validation, or molecular representations must be described explicitly.

## Model contributions

Do not add arbitrary `.joblib` files directly to the main repository.

A formal MolFlood Community Model Standard will define model-package metadata, validation requirements, licensing, provenance, security review, and acceptance criteria.

## Bug reports

Include MolFlood version, Python version, operating system, exact traceback, notebook section, and whether the problem persists after restarting the kernel and running from the beginning.

Do not upload confidential or restricted molecular datasets to public issues.

## License

Source-code contributions are distributed under the repository MIT License.
