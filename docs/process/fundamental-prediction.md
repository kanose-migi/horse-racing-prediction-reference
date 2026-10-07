# B1. Fundamental Prediction

## 目的

市場価格とは独立または分離した形で、馬・騎手・調教師・レース条件等から競走結果の確率・scoreを推定します。

## 競馬分野のアプローチ

- Logistic Regression
- Random Forest
- XGBoost
- LightGBM
- CatBoost

近年の公開競馬実装でもGBDTは依然として強いbaselineです。

## 他分野からの転用候補

- TabPFN
- TabICL
- TabICLv2
- その他Tabular Foundation Models

## 評価観点

LogLoss、Brier、ROC-AUC、PR-AUC、Top-k等。必ずmarket-only baselineとも比較します。

## 注意点

prediction accuracyの改善はprofitabilityを保証しません。

## 関連ページ

[Market Modeling](market-modeling.md) / [Probability Calibration](probability-calibration.md)
