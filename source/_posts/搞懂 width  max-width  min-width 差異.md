---
title: "搞懂 width / max-width / min-width 差異"
date: 2022-03-27T01:59:00.000-07:00
tags:

categories:
  - 舊部落格移植文章
---

# 搞懂 width / max-width / min-width 差異

原文連結: https://appcs342.blogspot.com/2022/03/width-max-width-min-width.html
移植時的最後更新日期: 2022-03-27T01:59:21.653-07:00

<p>原本自己以為是很簡單的觀念，不過最近被問後發現其實並沒有很了解，像是我沒去思考過假如width跟max-width都設定數值，互相衝突後會發生什麼事情。所以我打算重新研究後，整理筆記出來。<br /><br /></p><h2 style="text-align: left;">width(寬度）</h2><div><ul style="text-align: left;"><li>用來設定物件的寬</li><li>網頁頁面一定會用到的屬性</li></ul><br /></div><h2 style="text-align: left;">max-width(最大寬度值）</h2><div><ul style="text-align: left;"><li>用來給物件設定最大寬度值</li><li>適用於尺寸限制時</li></ul><br /></div><div><h2>min-width(最小寬度值）</h2><div><ul><li>用來給物件設定最小寬度值</li><li>適用於尺寸限制時</li></ul><br /></div></div><h2 style="text-align: left;">衝突時的狀況</h2><div>結論：會以更加明確的那個狀況為優先。</div><div>舉例來說，假如給一個物件10單位的寬度（width)，又指定給這個物件最小寬度為20單位(min-width)，這時候就會產生衝突的狀況。最後的結果會是最小寬度更為優先，所以是20單位。</div><div><span style="color: red;">在這狀況下，min-width會覆蓋width的值，我自己是理解成</span><span style="color: red;">min-width意味著最少就是需要這樣的寬度值，所以假如width設定的寬度值少於</span><span style="color: red;">min-width就會失去效果。</span></div><div><span style="color: red;"><br /></span></div><div><span style="color: red;"><br /></span></div><h2 style="text-align: left;">小結</h2><div><span style="font-family: inherit;">寬度通常都會擇一使用，很少會遇到&nbsp;width / max-width / min-width 同時混再一起使用，因為這樣不只可讀性變得怪怪的，邏輯也會不太通。然後還有width因為比較基本，所以通常混用時，常常會被&nbsp;max-width / min-width 覆蓋效果，所以要讓width<span style="background-color: white;">正常發揮它的作用，最簡單的方式就是只下</span>width就好。</span><br /><br /></div><h2 style="text-align: left;">參考資料</h2><div><a href="https://ithelp.ithome.com.tw/articles/10252194">https://ithelp.ithome.com.tw/articles/10252194</a><br /></div><div><br /></div><div><a href="https://developer.mozilla.org/zh-CN/docs/Web/CSS/max-width">https://developer.mozilla.org/zh-CN/docs/Web/CSS/max-width</a><br /></div><div><br /></div>
