# D. Learning Loop

## Goal

予測と判断の結果を評価し、環境変化を検知しながら次のモデル・校正・意思決定へ反映します。

## Processes

1. [Evaluation](../process/evaluation.md)
2. [Shadow Operation](../process/shadow-operation.md)
3. [Online Adaptation](../process/online-adaptation.md)

## Key idea

競馬は時系列で繰り返し意思決定する問題です。ランダムsplitの一回評価より、walk-forward、future holdout、shadow operation、drift detection、rolling recalibrationを重視します。
