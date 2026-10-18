---
title: CSVの配置
weight: 3
---

## データフォルダ
CsvCftは、EXEと同じ場所の `data\daily` をデータフォルダとして認識します。

※ データフォルダのパスは、設定ファイルで変更することができます。


## 変換前CSV
データフォルダに、変換前のCSVを配置します。

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

データフォルダ内の要素について、以下に説明を記載していきます。

### mb（データソースフォルダ）
名前は任意ですが、データソースに対応したCSV変換を行うため、変換定義に記載されたプレフィックスと一致している必要があります。

デフォルトの変換定義を使用する場合、データソースがあらかじめ定義されています。[デフォルトの変換定義]({{< ref "default-def.md" >}}) をご確認の上、対応する名前のフォルダを作成して頂ければと思います。

### mb-acwi（銘柄フォルダ）
名称は「`データソース名-商品識別名`」で、半角ハイフンで2つの名前を区切ります。商品識別名は、自由に付けることができます。

### mb-acwi.csv（変換前CSV）
名称は「`銘柄フォルダ名.csv`」にする必要があります。今回の「acwi」は、オルカンを示す名称となっています。


## 変換後CSV
アプリで変換を実行すると、「`銘柄フォルダ名-fmt.csv`」が出力されます。

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
      {{< filetree/folder name="yf" state="open" >}}
        {{< filetree/folder name="yf-qqq" state="open" >}}
          {{< filetree/file name="yf-qqq.csv" >}}
        {{< /filetree/folder >}}
      {{< /filetree/folder >}}
    {{< /filetree/folder >}}
  {{< /filetree/folder >}}
{{< /filetree/container >}}