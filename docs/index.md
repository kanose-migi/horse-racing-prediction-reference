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

| Layer（層） | Process（工程） | 競馬分野の主なアプローチ | 他分野からの転用候補 |
|---|---|---|---|
| A | [Data Acquisition（データ取得）](process/data-acquisition.md) | 出馬表・過去走・オッズ・投票・調教・血統データ | Event streaming, CDC, event sourcing |
| A | [Point-in-Time Integrity〈予測時点における情報整合性〉](process/point-in-time-integrity.md) | 時系列holdout、future leakage〈未来情報の混入〉防止 | As-of join, bitemporal data, point-in-time feature store |
| A | [Preprocessing（前処理）](process/preprocessing.md) | 欠損処理、target encoding、race-relative normalization〈レース内相対正規化〉 | Entity embedding, learned encoding |
| A | [Feature Engineering（特徴量設計）](process/feature-engineering.md) | 過去N走、適性、Speed/Form rating〈走破能力・近況を数値化したレーティング〉、騎手・調教師成績 | Elo, TrueSkill, opponent-strength adjustment〈対戦相手の強さによる補正〉 |
| A | [Representation Learning（表現学習）](process/representation-learning.md) | 過去走LSTM/Attention、血統集約 | Event Transformer, GNN, LLM feature extraction |
| B | [Fundamental Prediction〈［競走能力・条件要因などの］基礎要因に基づく予測〉](process/fundamental-prediction.md) | Logistic, XGBoost, LightGBM, CatBoost | TabPFN, TabICL, TabICLv2 |
| B | [Ranking（順位付け）](process/ranking.md) | LambdaRank, LightGBM/CatBoost/XGBoost Ranker | Full-order probabilistic ranking〈全着順を対象とする確率的順位付け〉, FOB |
| B | [Probability Calibration（確率校正）](process/probability-calibration.md) | Platt, Isotonic, Temperature Scaling | Online/adaptive calibration〈逐次・適応的な確率校正〉 |
| B | [Market Modeling〈市場・価格形成のモデル化〉](process/market-modeling.md) | implied probability〈オッズから逆算した確率〉, de-vig〈控除分を除いて市場確率へ補正する処理〉, odds movement（オッズ変動）, Benter-style blending〈予測確率と市場確率の統合〉 | Chronos-2, TimesFM, market-event/LOB models |
| C | [Uncertainty / Selection（不確実性 / 選択）](process/uncertainty-selection.md) | race difficulty（レース難易度）, upset risk〈波乱が起きるリスク〉, ensemble disagreement〈アンサンブル内の予測不一致〉 | Selective Prediction（選択的予測）, Conformal Prediction（共形予測）, Conformal Risk Control（共形リスク制御） |
| C | [Ticket Probability〈買い目の的中確率〉](process/ticket-probability.md) | Harville, Henery, Plackett-Luce, Monte Carlo（モンテカルロ法） | permutation models（順列モデル）, full-order distributions〈全着順の確率分布〉 |
| C | [Decision Optimization（意思決定最適化）](process/decision-optimization.md) | EV threshold（期待値閾値）, value betting〈市場価格に対して割安な買い目を選ぶ投票〉 | Decision-Focused Learning〈下流の意思決定損失を直接考慮する学習〉, Predict-then-Optimize〈予測後に最適化する枠組み〉, regret minimization（後悔最小化） |
| C | [Bankroll / Risk〈資金管理 / リスク管理〉](process/bankroll-risk.md) | Kelly（ケリー基準）, Fractional Kelly〈ケリー基準より抑制した賭け金配分〉, exposure caps〈投資額・リスク量の上限制約〉 | portfolio optimization, CVaR, robust optimization |
| D | [Evaluation（評価）](process/evaluation.md) | walk-forward〈時系列順に学習・評価期間を前進させる検証〉, temporal OOS〈時間順に分離した未学習期間での評価〉, ROI（回収率）, Brier, LogLoss, NDCG | purged CV〈学習・評価間の時間的重複を除く交差検証〉, bootstrap CI（ブートストラップ信頼区間）, multiple-testing correction（多重検定補正） |
| D | [Shadow Operation〈実取引を伴わない並行運用〉](process/shadow-operation.md) | 仮想購入、実運用前の予測記録 | shadow deployment〈本番データを使うが意思決定には反映しない並行展開〉, champion/challenger〈現行モデルと候補モデルの並行比較〉, canary evaluation〈限定的な範囲で新方式を試す評価〉 |
| D | [Online Adaptation〈運用中の逐次適応〉](process/online-adaptation.md) | rolling retraining〈時間窓を更新しながら行う再学習〉, recalibration（再校正） | drift detection〈データ分布・予測関係の変化検知〉, Test-Time Adaptation〈推論時にモデルを環境へ適応させる手法〉, online learning |

## Reading guide

- 全体像から読む: [Architecture](architecture/index.md)
- 工程単位で調べる: [Process](process/index.md)
- 手法名から調べる: [Technologies](technologies/index.md)
- 用語を確認する: [Glossary](glossary/index.md)
- 根拠・実装例を辿る: [Sources](sources/index.md)

## Editorial policy

- **一般論として記述する。** 特定システム固有の設計・実験結果・秘密情報は原則として扱わない。
- **Prediction（予測） と Decision（意思決定）を分離する。** 的中精度と収益性を同一視しない。
- **時点整合性を重視する。** 実運用時点で取得不能な情報を用いた評価を高く扱わない。
- **市場を強いbaseline〈比較基準〉として扱う。** オッズを単なる特徴量ではなく、市場の集合知として比較対象にする。
- **新規性と実証を分ける。** 新しい手法であることと、競馬で有効であることを区別する。
