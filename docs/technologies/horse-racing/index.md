# Horse-racing approaches

競馬研究・公開実装で利用実績が確認できる代表的な方法を整理します。

| Area | Approaches | Typical role |
|---|---|---|
| Tabular prediction | Logistic Regression, XGBoost, LightGBM, CatBoost | 勝率・複勝率・score |
| Ranking | LambdaRank, LightGBM/CatBoost/XGBoost Ranker | レース内順位 |
| Calibration | Platt, Isotonic, Temperature Scaling | score → usable probability |
| Market | implied probability, de-vig, odds movement, Benter-style blending | 市場評価との比較 |
| Ordered tickets | Harville, Henery, Plackett-Luce, Monte Carlo | 馬単・三連単等 |
| Selection | EV / confidence threshold, race-difficulty model | BET / SKIP |
| Bankroll | Kelly / Fractional Kelly | bet sizing |
| Validation | temporal split, walk-forward, future holdout | 実運用近似評価 |

個別技術ページは今後、論文・OSSの根拠とともに追加します。
