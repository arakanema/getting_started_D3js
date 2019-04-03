---
layout: page
title:  "データを描画する"
toc: true
---

このページで利用するサンプルファイル
- [sample.csv](/data/sample.csv)

      name,points
      Hiroshi,90
      Takeshi,88
      Sayaka,93
      Shinzou,80
      Tarou,80
      Jirou,70

とりあえず、一番よく使いそうなcsvファイルを使ってすすめていきます。

まずは、d3を使って描画するDOM要素を記述します。

```html
<div id="d3area"></div>
```

この要素内に、dataとして渡されたオブジェクトを使って描画してみました。

<div id="d3area"></div>
<script src="https://d3js.org/d3.v5.min.js"></script> 
<script type="text/javascript">
  d3.csv("/data/sample.csv").then(function(data) {
    console.log(data); // とりあえずログとして吐いておきます

    // svg要素を追加
    var svg = d3.select("#d3area").append("svg")
      .attr("width", 500)
      .attr("height", 100);

    // circlesにdataをマッピング
    // データの数と同じだけの circle を扱うということ
    // 肝はselectAllです、実は
    var circles = svg.selectAll("circle")
      .data(data);

    // enterというメソッドの中では、各データに対しての処理を書きます
    circles.enter()
      .append("circle")
        .attr("cx", function(d, i) {
          // iはインデックス、dは一つのデータ
          return i * d.points + d.points / 2;
        })
        .attr("cy", 50)
        .attr("r", function(d) {
          return d.points / 2;
        })
        .attr("fill", function(d) {
          // 以下のようにデータを使うこともできます
          if (d.name == "Tarou") {
            return "green";
          } else {
            return "red";
          }
        });
  });
</script>

```js
<script src="https://d3js.org/d3.v5.min.js"></script> 
<script type="text/javascript">
  d3.csv("/data/sample.csv").then(function(data) {
    console.log(data); // とりあえずログとして吐いておきます

    // svg要素を追加
    var svg = d3.select("#d3area").append("svg")
      .attr("width", 500)
      .attr("height", 100);

    // circlesにdataをマッピング
    // データの数と同じだけの circle を扱うということ
    // 肝はselectAllです、実は
    var circles = svg.selectAll("circle")
      .data(data);

    // enterというメソッドの中では、各データに対しての処理を書きます
    circles.enter()
      .append("circle")
        .attr("cx", function(d, i) {
          // iはインデックス、dは一つのデータ
          return i * d.points + d.points / 2;
        })
        .attr("cy", 50)
        .attr("r", function(d) {
          return d.points / 2;
        })
        .attr("fill", function(d) {
          // 以下のようにデータを使うこともできます
          if (d.name == "Tarou") {
            return "green";
          } else {
            return "red";
          }
        });
  });
</script>
```

このように、データを読み込んだ後、データをDOM要素にマッピングする機能をd3は提供しています。

しかしながら、まだまだビジュアライゼーションには程遠い感じがしますね...

d3は柔軟にビジュアライズできるが故に、一般的なチャートライブラリより少し手がかかりますが、次以降に紹介する基本的な作法を抑えておけば、痒いところに手が届く素晴らしいツールとして使いこなすことができます。

次はd3における重要なスケールと軸について見てみましょう！

[スケールと軸を扱う](/04_scales_and_axes/)
