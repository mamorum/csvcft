---
title: 概要
weight: 1
---

## CsvCft とは？
CsvCftは、アセットの日次CSVを共通的な形式に変換・整形するツールです。

変換後のCSVは、以下の列で構成されます。

- Date: 日付
- Close: 終値 or 基準価額
- Dividends: 配当金 or 分配金

内容は、日付の昇順となります。

```csv {filename="例: 変換後CSV"}
Date,Close,Dividends
2026-06-15,10401,120
2026-06-16,10428,0
```


## 動作環境
- OS: Windows11 64bit
- CPU: AMD / Intel
