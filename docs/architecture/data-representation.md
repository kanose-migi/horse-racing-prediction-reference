# A. Data / Representation

## Goal

レース時点の現実世界を、予測モデルが利用できる情報へ変換します。モデル精度以前に、**何を知っていたか** と **どのような表現で渡すか** を決める層です。

## Processes

1. [Data Acquisition](../process/data-acquisition.md)
2. [Point-in-Time Integrity](../process/point-in-time-integrity.md)
3. [Preprocessing](../process/preprocessing.md)
4. [Feature Engineering](../process/feature-engineering.md)
5. [Representation Learning](../process/representation-learning.md)

## Key idea

競馬分野ではドメイン知識による特徴量設計が依然強力です。一方で、Event Transformer、GNN、LLM等を **特徴量の代替ではなくrepresentation generatorとして使う** 方向が転用候補になります。
