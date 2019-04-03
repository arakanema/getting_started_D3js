---
layout: page
title:  "D3.jsの使い方"
toc: true
---

D3はJavaScriptライブラリなので、例に漏れず \<script\> タグを使って読み込みます。

当たり前の話ですが、D3を読み込んだ後でなければD3の機能を使うことはできないので、ソースに記述する順番には気をつけよう！

```html
<!-- 描画するDOM要素（後から追加もできる）-->
<div id="chart"></div>

<!-- d3を読み込み（CDNからとかローカルからとか） -->
<script src="https://d3js.org/d3.v5.min.js"></script> 

<!-- d3読み込み後にDOM操作を記述する -->
<script type="text/javascript">
  // ここに色々と記述する
</script>
``` 

次にデータを読み込む方法を確認しましょう！

[データを読み込む](/02_load_data/)
