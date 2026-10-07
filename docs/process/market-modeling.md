# B4. Market Modeling

## 目的

オッズ・投票情報を、市場参加者の集合的評価としてモデル化します。

## 競馬分野のアプローチ

- implied probability (`1 / odds`)
- de-vig / 控除補正
- 人気・オッズ順位
- オッズ変動、late money、投票share
- Fundamental probabilityとMarket probabilityの比較・blending（Benter型）

## 他分野からの転用候補

### Time-series foundation models

- Chronos-2
- TimesFM系
- multivariate time-series forecasting

### Market microstructure

- event-based market models
- LOB Transformer
- TradeFM系のmarket-event foundation model

## 応用例

T-60 → T-30 → T-15 → T-5のオッズ系列から締切時のmarket probabilityや急変を予測する。

## 評価観点

市場確率に対するLogLoss / Brier、final odds forecast error、edgeの安定性。

## 注意点

市場オッズは非常に強いbaselineです。「オッズを使うと当たる」ことと「市場より優れた価格発見をする」ことを区別します。
