# C2. Ticket Probability

## 目的

単勝確率や馬のscoreから、馬連・馬単・三連複・三連単等のjoint / order probabilityを推定します。

## 競馬分野のアプローチ

- Harville model
- Henery adjustment
- Plackett-Luce
- Monte Carlo race simulation

## 他分野からの転用候補

- permutation distribution models
- full-order probabilistic ranking
- generative ranking / simulation

## 評価観点

券種ごとのproper scoring、順位分布のfit、calibration、実オッズとの比較。

## 注意点

各馬の独立な勝率だけから組合せ確率を単純積で計算することはできません。
