# Interpreting MolFlood Results

## Metrics

- RMSE: prediction error in docking-score units with stronger penalty for large errors.
- MAE: average absolute prediction error.
- R²: held-out variation explained relative to a mean-based reference.
- Spearman: agreement in molecular ranking.

## Applicability domain

Higher Morgan/Tanimoto similarity to training chemistry indicates stronger structural support. Outside-domain predictions represent stronger extrapolation.

## Limits

MolFlood does not establish experimental binding, cellular activity, selectivity, toxicity, pharmacokinetics, or therapeutic efficacy.
