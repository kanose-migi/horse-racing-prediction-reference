# B3. Probability Calibration

## 目的

モデルが出す0.2、0.5、0.8等の確率と、実際の発生頻度を一致させます。

## 競馬分野のアプローチ

- Platt Scaling
- Isotonic Regression
- Temperature Scaling
- reliability diagram
- Brier Score / ECE / LogLoss

## 他分野からの転用候補

- online calibration
- adaptive calibration
- distribution-shift-aware calibration

## 評価観点

Brier、LogLoss、ECE、calibration curveを時系列OOSで評価します。

## 注意点

EVやKellyは確率誤差に敏感なため、ランキング精度だけでbetting modelを評価しないことが重要です。
