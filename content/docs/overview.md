---
title: 概要
weight: 1
---

## CsvCftとは？
CsvCftは、アセットの日次CSVを共通的な形式に変換・整形するツールです。

変換後のCSVは、以下の列で構成されます。

- Date: 日付
- Close: 終値, 基準価額
- Dividends: 配当金, 分配金

データは日付の昇順となり、数値のカンマ区切りは削除されます。

```csv {filename="変換後CSV"}
Date,Close,Dividends
2026-06-09,10401,120
2026-06-10,10428,0
```


## 動作環境
- OS: Windows11 64bit
- CPU: AMD / Intel
