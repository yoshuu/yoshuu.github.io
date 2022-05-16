---
title: "Selector Combinators 中的+跟~差別"
date: 2022-04-04T05:40:00.000-07:00
tags:
  - css
categories:
  - 舊部落格移植文章
---

原文連結: https://appcs342.blogspot.com/2022/04/selector-combinators.html
移植時的最後更新日期: 2022-04-04T05:40:13.467-07:00

<!--more-->
<div><span style="font-family: inherit;">介紹兩個很類似的選擇器，</span></div><span style="font-family: inherit;">全名是Next-sibling combinator，簡稱加號(+)</span><div><span style="font-family: inherit;">全名是Subsequent-sibling combinator，簡稱波浪號(~)</span></div><div><span style="font-family: inherit;"><br /></span></div><div><ul style="text-align: left;"><li><span style="font-family: inherit;">加號是會影響到後方同層級的首次遇到元素</span></li><li><span style="font-family: inherit;">波浪號則是影響後方同層級的全部元素</span></li></ul><div><span style="font-family: inherit;"><br /></span></div></div><div><span style="font-family: inherit;">加號跟波浪號都是目標為要影響後方同層級，語法使用方式也都差不多</span></div><div><span style="font-family: inherit;">[選取對象A + 選取對象B] 及 [選取對象A ~ 選取對象B]。</span></div><div><span style="font-family: inherit;"><br /></span></div><div><span style="font-family: inherit;"><br /></span></div><div><span style="font-family: inherit;">看起來非常的像，不過有一些差別：</span></div><div><ul style="text-align: left;"><li>加號是只能選到A後面那一個B</li><li>波浪號是選到A後面整串同層的B</li></ul></div>
