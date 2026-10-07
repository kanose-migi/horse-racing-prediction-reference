# A1. Data Acquisition

## 目的

予測時点で利用可能な競馬情報を、後から再現可能な形で取得・保存します。

## 入力 / 出力

**入力:** 公式データ、出馬表、過去走、オッズ、投票情報、天候・馬場、調教・コメント等  
**出力:** timestampとsourceを保持したraw / normalized data

## 競馬分野のアプローチ

- JRA-VAN / JV-Link等の公式・準公式データサービス
- HKJC等の公開race card / result取得
- 過去走、馬、騎手、調教師、血統、斤量、馬体重、馬場、オッズ
- T-60 / T-30 / T-15 / T-5等のオッズsnapshot保存

## 他分野からの転用候補

- Event streaming
- Change Data Capture (CDC)
- Event sourcing
- 金融tick-data型のappend-only保存

## 評価観点

coverage、欠損率、timestamp精度、再現性、更新遅延。

## 注意点

最終値だけ保存すると「その時点で何を知っていたか」を再現できません。特にオッズは時系列として保存する価値があります。

## 関連ページ

[Point-in-Time Integrity](point-in-time-integrity.md) / [Market Modeling](market-modeling.md)
