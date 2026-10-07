# Architecture

競馬予測を単一の「勝馬予測モデル」としてではなく、4つの大きな層からなる意思決定システムとして整理します。

| Layer | Question | 主な小工程 |
|---|---|---|
| [A. Data / Representation](data-representation.md) | 何を観測し、どう表現するか | 取得、時点整合、前処理、特徴量、表現学習 |
| [B. Forecasting](forecasting.md) | 何が起きると予測するか | Fundamental、Ranking、Calibration、Market |
| [C. Decision](decision.md) | 予測から何をするか | 不確実性、BET/SKIP、券種確率、最適化、資金管理 |
| [D. Learning Loop](learning-loop.md) | 結果からどう改善するか | OOS評価、Shadow、Drift、再校正・再学習 |

この分割の目的は、新しい技術を導入するときに「どの問題を解く技術か」を明確にすることです。例えばTabular Foundation Modelは主にForecasting、Conformal Predictionは主にDecision、Test-Time AdaptationはLearning Loopに属します。
