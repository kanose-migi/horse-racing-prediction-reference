# D3. Online Adaptation

## 目的

季節・開催・馬場・参加者・市場構造等のdistribution shiftに対応します。

## 競馬分野のアプローチ

- rolling retraining
- 定期recalibration
- 開催・条件別performance monitoring

## 他分野からの転用候補

- drift detection (PSI, MMD等)
- change-point detection
- online calibration
- Test-Time Adaptation (TTA)
- continual / online learning

## 評価観点

適応前後のfuture performanceと、過適応・catastrophic forgettingの有無を評価します。

## 注意点

新しいデータへ適応することと、直近ノイズに追随することを区別します。
