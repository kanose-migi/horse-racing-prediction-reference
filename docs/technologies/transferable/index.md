# Transferable approaches

競馬以外の分野で発展し、競馬予測の各工程へ転用可能性がある方法です。

| Origin | Technology / approach | Possible horse-racing use |
|---|---|---|
| Tabular ML | TabPFN, TabICL, TabICLv2 | Fundamental model challenger |
| Search / Ranking | full-order probabilistic ranking, FOB | 完全着順分布・組合せ確率 |
| Safety / Uncertainty | Selective Prediction, Conformal Prediction, Conformal Risk Control | BET / SKIP、risk-controlled selection |
| Operations Research | Decision-Focused Learning, Predict-then-Optimize | ticket selection / regret minimization |
| Time Series | Chronos-2, TimesFM系 | オッズ時系列・締切価格予測 |
| Market Microstructure | LOB Transformer, TradeFM系 | late money / market event modeling |
| Sequence Modeling | Event Transformer | horse history representation |
| Graph ML | GNN, Graph Transformer | pedigree representation |
| NLP / LLM | structured information extraction | 調教・厩舎・騎手コメント特徴量化 |
| Production ML | Test-Time Adaptation, online calibration | drift / deployment adaptation |
| Portfolio / Risk | CVaR, robust optimization | bankroll allocation |

「新しい」ことと「競馬で有効」なことは分けて評価します。
