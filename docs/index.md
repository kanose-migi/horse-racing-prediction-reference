# Horse Racing Prediction Reference

競馬予測を **データ → 予測 → 意思決定 → 学習ループ** として分解し、各工程について次の2方向から技術を整理するリファレンスです。

1. **競馬分野** — 競馬研究・公開実装で既に使われている、または検証されている方法
2. **転用候補** — 金融、推薦、時系列、Operations Research、安全AI、汎用MLなどで発達し、競馬へ転用できる可能性がある方法

特定の競馬予測システムの仕様や実装判断ではなく、一般的な知識の整理を目的とします。

## Architecture

```text
A. DATA / REPRESENTATION
「現実世界をモデルが扱える状態にする」
              │
              ▼
B. FORECASTING
「馬・順位・市場がどうなるかを予測する」
              │
              ▼
C. DECISION
「予測を使って何をするか決める」
              │
              ▼
D. LEARNING LOOP
「結果を評価し、次の予測・判断へ反映する」
              └──────────→ A / B / C
```

## Technology map

| Layer | Process | 競馬分野の主なアプローチ | 他分野からの転用候補 |
|---|---|---|---|
| A | [Data Acquisition](process/data-acquisition.md) | 出馬表・過去走・オッズ・投票・調教・血統データ | Event streaming, CDC, event sourcing |
| A | [Point-in-Time Integrity](process/point-in-time-integrity.md) | 時系列holdout、future leakage防止 | As-of join, bitemporal data, point-in-time feature store |
| A | [Preprocessing](process/preprocessing.md) | 欠損処理、target encoding、race-relative normalization | Entity embedding, learned encoding |
| A | [Feature Engineering](process/feature-engineering.md) | 過去N走、適性、Speed/Form rating、騎手・調教師成績 | Elo, TrueSkill, opponent-strength adjustment |
| A | [Representation Learning](process/representation-learning.md) | 過去走LSTM/Attention、血統集約 | Event Transformer, GNN, LLM feature extraction |
| B | [Fundamental Prediction](process/fundamental-prediction.md) | Logistic, XGBoost, LightGBM, CatBoost | TabPFN, TabICL, TabICLv2 |
| B | [Ranking](process/ranking.md) | LambdaRank, LightGBM/CatBoost/XGBoost Ranker | Full-order probabilistic ranking, FOB |
| B | [Probability Calibration](process/probability-calibration.md) | Platt, Isotonic, Temperature Scaling | Online/adaptive calibration |
| B | [Market Modeling](process/market-modeling.md) | implied probability, de-vig, odds movement, Benter-style blending | Chronos-2, TimesFM, market-event/LOB models |
| C | [Uncertainty / Selection](process/uncertainty-selection.md) | race difficulty, upset risk, ensemble disagreement | Selective Prediction, Conformal Prediction, Conformal Risk Control |
| C | [Ticket Probability](process/ticket-probability.md) | Harville, Henery, Plackett-Luce, Monte Carlo | permutation models, full-order distributions |
| C | [Decision Optimization](process/decision-optimization.md) | EV threshold, value betting | Decision-Focused Learning, Predict-then-Optimize, regret minimization |
| C | [Bankroll / Risk](process/bankroll-risk.md) | Kelly, Fractional Kelly, exposure caps | portfolio optimization, CVaR, robust optimization |
| D | [Evaluation](process/evaluation.md) | walk-forward, temporal OOS, ROI, Brier, LogLoss, NDCG | purged CV, bootstrap CI, multiple-testing correction |
| D | [Shadow Operation](process/shadow-operation.md) | 仮想購入、実運用前の予測記録 | shadow deployment, champion/challenger, canary evaluation |
| D | [Online Adaptation](process/online-adaptation.md) | rolling retraining, recalibration | drift detection, Test-Time Adaptation, online learning |

## Reading guide

- 全体像から読む: [Architecture](architecture/index.md)
- 工程単位で調べる: [Process](process/index.md)
- 手法名から調べる: [Technologies](technologies/index.md)
- 用語を確認する: [Glossary](glossary/index.md)
- 根拠・実装例を辿る: [Sources](sources/index.md)

## Editorial policy

- **一般論として記述する。** 特定システム固有の設計・実験結果・秘密情報は原則として扱わない。
- **Prediction と Decision を分離する。** 的中精度と収益性を同一視しない。
- **時点整合性を重視する。** 実運用時点で取得不能な情報を用いた評価を高く扱わない。
- **市場を強いbaselineとして扱う。** オッズを単なる特徴量ではなく、市場の集合知として比較対象にする。
- **新規性と実証を分ける。** 新しい手法であることと、競馬で有効であることを区別する。
