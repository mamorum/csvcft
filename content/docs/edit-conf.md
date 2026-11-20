---
title: 設定ファイルの編集
weight: 8
---

## 設定の追加
EXEと同じ場所に `cft-conf.ini` を追加すると、アプリの設定を行うことができます。

設定は「`項目名=値`」で追加できます。

```
DataDir=D:\invest\csv\daily
InitTicker=mb-spx
```

## 設定項目・値
### DataDir
データフォルダの絶対パスを指定します。

### InitTicker
銘柄エリアの初期値を指定します。


## エンコーディング 
設定ファイルは、「UTF-8」にする必要があります。
