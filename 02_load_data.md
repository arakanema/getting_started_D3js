---
layout: page
title:  "データを読み込む"
toc: true
---

D3はカンマ区切りのcsvファイル、タブ区切りのtsvファイル、そしてjsonファイルを標準で上手く取り回す機能を提供しています。

サンプルファイル
- [sample.csv](/data/sample.csv)
- [sample.tsv](/data/sample.tsv)
- [sample.json](/data/sample.json)

それぞれのデータ形式は以下のようにしてオブジェクトとして読み込まれます。

```js
d3.csv("/data/sample.csv").then(function(data) {
  // 以下に data を使ったプロセスを書く
});

d3.tsv("/data/sample.tsv").then(function(data) {
  // 以下に data を使ったプロセスを書く
});

d3.json("/data/sample.json").then(function(data) {
  // 以下に data を使ったプロセスを書く
});
```
<script src="https://d3js.org/d3.v5.min.js"></script> 
<script type="text/javascript">
  function loadExample() {
    d3.json("/data/sample.json").then(function(data) {
      alert(data);
      console.log(data);
    });
  }
  function loadExampleCSV() {
    d3.csv("/data/sample.csv").then(function(data) {
      alert(data);
      console.log(data);
    });
  }

</script>

**<a href="#" onClick="loadExample()">>> dataをアラート＆consolo.logしてみる(json) <<</a>**

Google Chromeのデベロッパーツールでログを確認してみてください。  
以下のように、JSONファイルから読み込めていることが確認できます。簡単ですね！

![読み込み確認](/assets/load_data_example.png "あら簡単！")

一応、CSVファイルでも試してみましょう！ 

**<a href="#" onClick="loadExampleCSV()">>> dataをアラート＆consolo.logしてみる(csv) <<</a>**

![読み込み確認](/assets/load_csv_data_example.png "なるほどcsv")

csvの例をよく見ると、JSONを読み込んだ時に生成されるオブジェクトには無い columns というメンバが存在しています。

まぁいずれにせよ、D3ではこのように簡単にデータをオブジェクトに変換できるので、静的なデータファイルやAPIで取得するjsonデータも容易に扱うことができるのです。

ということで次は読み込んだオブジェクトをどのようにして描画するのかを見てみましょう！

[データを描画する](/03_use_data/)
