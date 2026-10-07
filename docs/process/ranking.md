# B2. Ranking

## 目的

馬を独立分類するのではなく、同一レース内の相対順位を直接学習します。

## 競馬分野のアプローチ

- LambdaRank / LambdaMART
- LightGBM Ranker
- XGBoost Ranker
- CatBoost Ranker
- Plackett-Luce型順位モデル

## 他分野からの転用候補

- neural listwise ranking
- differentiable ranking
- full-order probabilistic ranking
- FOB (Full-Order Bound)

## 評価観点

NDCG、MAP、Top-k、race-level ranking metrics。betting用途では確率校正を別途確認します。

## 注意点

Rankerのscoreは通常そのまま勝率ではありません。softmax等で確率化してもcalibrationが良いとは限りません。
