# Glossary

## Calibration

予測確率と実際の発生頻度が一致する性質。20%と予測された事象群が概ね20%発生する状態。

## Brier Score

確率予測の二乗誤差を測るproper scoring rule。小さいほどよい。

## ECE

Expected Calibration Error。確率帯ごとの予測confidenceと実測frequencyのずれを要約する指標。

## De-vig

オッズに含まれる控除・marginの影響を除去し、市場の確率分布を推定する処理。

## Leakage

### Look-ahead leakage

予測時点より後に得られる情報を学習・評価で使用してしまうこと。

### Target leakage

目的変数またはその強い派生情報が特徴量へ混入すること。

## Walk-forward validation

過去で学習し、その直後の未来で評価する処理を時間方向へ繰り返す検証法。

## Learning to Rank (LTR)

個々のサンプル分類ではなく、グループ内の相対順位を学習する問題設定。競馬では1レースをquery/groupとみなせる。

## Selective Prediction

モデルが予測だけでなく、予測を棄却・保留する選択肢を持つ枠組み。

## Conformal Prediction

有限標本下でcoverage等の統計的保証を与えるprediction set / uncertainty quantificationの枠組み。

## Decision-Focused Learning (DFL)

予測誤差そのものではなく、その予測を使った下流意思決定のquality / regretを考慮して学習する考え方。

## Kelly Criterion

長期的な対数資産成長率を最大化する理論的bet sizing。推定確率誤差に敏感なため、実務ではFractional Kelly等が用いられる。

## Market-only baseline

馬固有特徴を使わず、オッズ等の市場情報のみで作るbaseline。競馬市場の集合知に対してモデルが本当に追加情報を持つかを測る。
