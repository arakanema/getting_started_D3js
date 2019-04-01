---
layout: page
title:  "D3.jsとは何か？"
toc: true
---

（以下、公式サイトより抜粋）  
D3.jsはデータに基づいて文書を操作するためのJavaScriptライブラリです。  

[D3.js - Data-Driven Documents](https://d3js.org/)

D3は、HTML、SVG、およびCSSを使用してデータをより役立てる助けをします。  
また、D3はWeb標準に重点を置いているため、強力なビジュアライゼーションコンポーネント・データ操作・DOM操作のアプローチを組み合わせることで、独自のフレームワークに縛られることなく、最新のブラウザの全機能を利用できます。

## 簡単なSVG描画の例

<div id="chart"></div>
<script src="https://d3js.org/d3.v5.min.js"></script> 
<script type="text/javascript">
  var svg = d3.select('#chart')
    .append('svg')
    .attr('width', 300)
    .attr('height', 300);

  var circle = svg.append('circle')
    .attr('cx', 150)
    .attr('cy', 150)
    .attr('r', 75)
    .attr('fill', 'red');
</script>

上の赤丸は、D3を使ってこのように描画しています。

```html
<!-- 描画するDOM要素をマークアップ-->
<div id="chart"></div>
<!-- d3を読み込み -->
<script src="https://d3js.org/d3.v5.min.js"></script> 
<!-- d3読み込み後にDOM操作を記述します -->
<script type="text/javascript">
  // svgとしてdiv#chartにsvgエレメントを追加
  var svg = d3.select('#chart')
    .append('svg')
    .attr('width', 300)
    .attr('height', 300);
  // svgにcircleを追加し赤色で塗りつぶし
  var circle = svg.append('circle')
    .attr('cx', 150)
    .attr('cy', 150)
    .attr('r', 75)
    .attr('fill', 'red');
</script>
```
最初の紹介ではデータを利用していませんが、D3ではこのような強力なDOM操作も提供されています。  
この機能に加え、データ操作も容易に行うことができるので様々なデータを自由にビジュアライズすることができるのです。

次から少しづつD3の使い方を解説していきます。  
[D3.jsの使い方](/01_how_to_use/)