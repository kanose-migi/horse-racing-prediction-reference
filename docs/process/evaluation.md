# D1. Evaluation

## 目的

実運用を模擬した時系列条件で、予測・校正・意思決定を評価します。

## 競馬分野のアプローチ

- future holdout
- walk-forward validation
- race-level split
- market-only baseline
- LogLoss / Brier / ECE / ROC-AUC / PR-AUC / NDCG
- ROI / profit / max drawdown / bet count / coverage

## 他分野からの転用候補

- purged time-series CV
- combinatorial purged CV
- race-level bootstrap confidence interval
- multiple-testing correction
- proper scoring rule中心のmodel comparison

## 評価の原則

1. 市場を強いbaselineとして置く
2. prediction metricとdecision metricを分ける
3. race単位の依存を壊さない
4. confidence intervalを併記する
5. hyperparameter探索に使った期間と最終testを分離する

## 注意点

高い的中率・AUCだけで収益性を主張しません。オッズ時点とprediction timeも固定します。
