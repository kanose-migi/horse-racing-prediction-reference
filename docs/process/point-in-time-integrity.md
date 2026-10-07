# A2. Point-in-Time Integrity

## 目的

予測時点より後に判明した情報が学習・評価へ混入するlook-ahead bias / leakageを防ぎます。

## 入力 / 出力

**入力:** timestamp付きraw data  
**出力:** 指定prediction timeで再現可能なfeature view

## 競馬分野のアプローチ

- season/dateベースのfuture holdout
- expanding / rolling集計
- leak-free target encoding
- race前に取得可能な情報だけを特徴量へ採用

## 他分野からの転用候補

- as-of join
- bitemporal data model
- point-in-time correct feature store
- 金融backtestのlook-ahead / survivorship bias管理

## 評価観点

「各特徴量がprediction time時点で取得可能だったこと」を機械的に説明できるか。

## 注意点

最終オッズ、確定馬場、結果反映済みrating等は、予測時刻によって利用可否が変わります。

## 関連ページ

[Evaluation](evaluation.md) / [Glossary: Leakage](../glossary/index.md#leakage)
