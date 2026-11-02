---
title: CSVの配置
weight: 5
---

## データフォルダ
デフォルトだと、EXEが配置された場所の `data\daily` がデータフォルダになります。

{{< filetree/container >}}
  {{< filetree/file name="cft-def.ini" >}}
  {{< filetree/file name="CsvCft.exe" >}}
  {{< filetree/folder name="data" state="open" >}}
    {{< filetree/folder name="daily" state="open" >}}
      {{< filetree/folder name="mb" state="open" >}}
        {{< filetree/folder name="mb-acwi" state="open" >}}
          {{< filetree/file name="mb-acwi.csv" >}}
          {{< filetree/file name="mb-acwi-fmt.csv" >}}
        {{< /filetree/folder >}}
      {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}

データフォルダ内の要素について、上の配置例を元に説明を記載します。

### データソースフォルダ（例: mb）
名前は半角英数で、変換定義に存在する名称と一致している必要があります。

### 銘柄フォルダ（例: mb-acwi）
名前は「`データソース-商品識別名`」で、商品識別名には半角英数と半角記号が使用できます。

### 変換元CSV（例: mb-acwi.csv）
名前は「`銘柄名.csv`」にする必要があります。

### 変換後CSV（例: mb-acwi-fmt.csv）
変換を実行すると「`銘柄名-fmt.csv`」が出力されます。


## 要素の追加
画面でCSVを選択して変換すると、各要素が自動的に作成されます。手動でフォルダを作成して、変換元CSVを配置しても大丈夫です。

{{< filetree/container >}}
  {{< filetree/folder name="data" state="open" >}}
    {{< filetree/folder name="daily" state="open" >}}
      {{< filetree/folder name="mb" state="open" >}}
        {{< filetree/folder name="mb-acwi" state="open" >}}
          {{< filetree/file name="mb-acwi.csv" >}}
        {{< /filetree/folder >}}
        {{< filetree/folder name="mb-spx" state="open" >}}
          {{< filetree/file name="mb-spx.csv" >}}
        {{< /filetree/folder >}}
      {{< /filetree/folder >}}
      {{< filetree/folder name="ns" state="open" >}}
        {{< filetree/folder name="ns-ndx" state="open" >}}
          {{< filetree/file name="ns-ndx.csv" >}}
        {{< /filetree/folder >}}
      {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}