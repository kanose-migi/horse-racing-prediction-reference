# C1. Uncertainty / Selection

## 目的

予測値だけでなく「その予測を採用すべきか」を評価し、BET / SKIPを含む選択を行います。

## 競馬分野のアプローチ

- race difficulty / upset-risk model
- confidence threshold
- ensemble disagreement
- entropy
- 荒れやすい条件の除外

## 他分野からの転用候補

- Selective Prediction
- Conformal Prediction
- Conformal Risk Control
- abstention / reject option

## 評価観点

coverageとriskのトレードオフ。全レースを予測する性能だけでなく、選択した集合上での誤差を評価します。

## 注意点

「confidence > 0.8」のような任意閾値と、誤差制御を目的としたselective methodは区別します。
