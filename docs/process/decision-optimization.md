# C3. Decision Optimization

## 目的

予測確率、市場価格、不確実性から、どの選択肢を採用するかを最適化します。

## 競馬分野のアプローチ

- expected value threshold
- value betting
- 券種別rule-based selection
- Fundamental probabilityとMarket probabilityのedge

## 他分野からの転用候補

- Decision-Focused Learning (DFL)
- Predict-then-Optimize
- regret minimization
- robust decision optimization

## 評価観点

予測誤差ではなくdecision utility / regretも評価します。

## 注意点

ROIを直接最大化するend-to-end学習はノイズへのoverfitが起こりやすいため、確率モデル・校正・optimizerを分離したbaselineが必要です。
