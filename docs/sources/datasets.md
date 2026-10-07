# Datasets

## Japan

### JRA-VAN Data Lab

JRAの競走・出馬・オッズ等を扱う代表的なデータサービス。時系列オッズを含むデータ項目はmarket modeling研究で特に重要です。

https://jra-van.jp/dlb/

## Hong Kong

### Hong Kong Jockey Club (HKJC)

公開race card / resultsを利用した研究・OSSが多数存在します。

https://racing.hkjc.com/

## Data requirements by research area

| Research area | Particularly important data |
|---|---|
| Fundamental model | race card + historical performances |
| Calibration | prediction snapshots + results |
| Market model | timestamped odds / pool / popularity |
| Market microstructure | high-frequency market snapshots / event deltas |
| Drift / online adaptation | long chronological history |
| Text / LLM features | pre-race comments with publication timestamps |

データソースを追加する際は、利用規約・再配布条件・取得時刻の再現性も記録します。
