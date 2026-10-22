---
title: CSVの配置
weight: 4
---

## データフォルダ
CsvCftは、EXEが配置された場所の `data\daily` をデータフォルダとして認識します。`data` フォルダを作成して、その下に `daily` フォルダを作成します。

※ 設定ファイルを使うと、データフォルダのパスを変更することができます。


## 変換元CSV
変換対象のCSVを、データフォルダに配置していきます。

{{< filetree/container >}}
  {{< filetree/file name="cft-def.ini" >}}
  {{< filetree/file name="CsvCft.exe" >}}
  {{< filetree/folder name="data" state="open" >}}
    {{< filetree/folder name="daily" state="open" >}}
      {{< filetree/folder name="mb" state="open" >}}
        {{< filetree/folder name="mb-acwi" state="open" >}}
          {{< filetree/file name="mb-acwi.csv" >}}
        {{< /filetree/folder >}}
      {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}

データフォルダ内の要素について、上の配置例を元に説明を記載します。

### mb：データソースフォルダ
変換定義のサンプルを使用する場合、データソースがあらかじめ定義されています。[変換定義のサンプル]({{< ref "sample-def.md" >}}) に存在する名称で、フォルダを作成していきます。

データソースに応じたCSV変換を行うため、変換定義に存在する名称と一致している必要があります。データソースを追加する場合、半角英数で名前を付けることができます。

### mb-acwi：銘柄フォルダ
名前は「`データソース-商品識別名`」で、半角ハイフンを使って2つの名前を区切ります。商品識別名は、半角英数と半角記号を使って付けることができます。

### mb-acwi.csv：変換元CSV
名前は「`銘柄名.csv`」にする必要があります。


## 変換後CSV
変換を実行すると、「`銘柄名-fmt.csv`」が出力されます。

{{< filetree/container >}}
  {{< filetree/folder name="mb-acwi" state="open" >}}
    {{< filetree/file name="mb-acwi.csv" >}}
    {{< filetree/file name="mb-acwi-fmt.csv" >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}


## 変換対象の追加
変換対象を追加する場合、対応するデータソースフォルダに、銘柄フォルダとCSVを追加していきます。

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