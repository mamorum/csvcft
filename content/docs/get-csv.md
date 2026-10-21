---
title: CSVの入手方法
weight: 9
---

## 投資信託
運用会社次第にはなりますが、ファンドの公式ページで設定来データ（日次CSV）をダウンロードすることができます。


## yfinance
以下のコードは、当日を除く最大期間の日次CSVを出力する例です。

```python {filename="mk_yfcsv.py"}
import sys
import yfinance as yf
from datetime import datetime
from zoneinfo import ZoneInfo

def main():
  ticker = sys.argv[1]
  mkcsv(ticker)

def mkcsv(ticker):
  # ダウンロード
  df = _history(ticker)
  # CSVに出力
  csv_name = _csv_name(ticker)
  df.to_csv(csv_name, date_format="%Y-%m-%d")

def _history(ticker):
  # 日次データを取得（昇順）
  now_ymd = _now_et_ymd()
  yt = yf.Ticker(ticker)
  df = yt.history(
    period="max", end=now_ymd, # Max, Excluding Today.
    auto_adjust=False, # Not Adjusted OHLC.
    actions=True  # + Dividend & Stock Splits Data.
  )
  # 調整後終値の列を削除
  df = df.drop("Adj Close", axis=1)
  # 念のためタイムゾーン情報を削除
  # サマータイムの誤差もあるため
  df.index = df.index.tz_localize(None)
  return df

def _now_et_ymd():
  # ETの現在日付を取得（東部時間）
  # EST,EDTは自動判別される（標準時,夏時間）
  ymd = datetime.now(
    ZoneInfo("America/New_York")
  ).strftime("%Y-%m-%d")
  return ymd

def _csv_name(ticker):
  # ハットとイコールを削除
  tk = ticker.replace("^", "").replace("=", "")
  tk = tk.lower() # 小文字に変換
  return f"yf-{tk}.csv" # 銘柄名.csv

if __name__ == "__main__":
  main()
```

コマンドプロンプトで以下を実行すると、`yf-sox.csv` が出力されます。

```
python mk_yfcsv.py ^^SOX
```

調整後価格を使いたい場合や、ティッカーの記号を削除したくない場合などもあると思います。そのため、上のスクリプトはあくまで例の1つになります。

### 実行準備
スクリプトを実行するためには、Python と yfinance をインストールする必要があります。インストール方法は、以下の記事が参考になると思います。

- <a target="_blank" href="https://web-dev.hatenablog.com/entry/python/windows/install">Python Windowsにインストールする方法</a>
- <a target="_blank" href="https://web-dev.hatenablog.com/entry/python/yfinance/install">Python yfinanceをインストールする方法</a>

Python の操作に慣れている方は、必要に応じて venv（仮想環境）の作成などもご検討ください。
