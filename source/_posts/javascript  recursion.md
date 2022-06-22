---
title: JavaScript 請解釋「遞迴」的概念
date: 2022-06-22 09:26:58
tags:
  - javascript
categories:
  - javascript
---

我們先來看一下遞迴(recursion)在 mdn 上面的定義：

<!--more-->

> 函式呼叫函式自己的行為，稱為遞迴、或是遞歸。它主要用於解決含有子問題的問題。遞迴函式會收到兩個輸入：結束遞迴的基本情況（base case）或是延續遞迴的遞迴情況（recursive case）。

簡單來說，就是一種自己定義自己的意思，利用自己定義自己來解決問題，通常需要被遞迴的問題是一個可以被分成很多小問題的大問題。

可以使用迴圈解決的問題，也可以用遞迴來做解決，原本只會使用迴圈的我，想不通幹嘛要用遞回，後來想想其實多了一種新的解決問題的方式是一件好事。

會想要特別寫遞迴是因為一開始看不太懂，但突然看著看著就有了一些概念覺得蠻特別的，所以就來試著講解做個紀錄。

## 一個基本的遞迴會需要有：

1. 終止條件
2. 遞迴條件

第一個是因為假如沒有終止條件，那函式不斷的呼叫自己，最後就會變得沒完沒了，程式將無窮無盡不會結束。

而遞迴條件就是呼叫自已的條件，沒有終止條件就會無限循環然後當掉，但是沒有遞迴條件就沒辦法呼叫自己，程式就不知道怎麼呼叫。

## 遞迴小故事：

> 從前有座山，山裡有個廟，廟裡有個老和尚在給小和尚講故事，講的是從前有座山，山裡有個廟，廟裡有個老和尚在給小和尚講故事，講的是從前有座山。。。

出處：https://iter01.com/9337.html

## 遞迴裡面有個經典的例子：費氏數列

![](https://i.imgur.com/ypKel4Q.png)
以費波那契數為邊的正方形拼成的近似的黃金矩形
圖片來源：https://zh.m.wikipedia.org/zh-tw/%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91%E6%95%B0

在數學上，費波那契數是以遞迴的方法來定義：

- f0=0 (1)
- f1=1 (2)
- Fn = Fn-1+Fn-2 (3)

其中(1)跟(2)就是上述提到的終止條件，而(3)是遞回的定義

簡單來說，費式數列是從零開始，之後的數字都是由前面的數字兩者相加而成：

```
1、 1、 2、 3、 5、 8、 13、 21、 34、 55、 89、 144、 233、 377、 610
```

使用 JavaScript 迴圈的寫法來寫：

```javascript=
function fibonacci(n) {
  if (n < 2) {
    return n;
  }
  return fibonacci(n - 1) + fibonacci(n - 2);
}
```

## 小結

寫的比較簡單，但是遞迴其實還有很多東西可以講的，待日後我懂更多後再回來補充吧

最後分享一下我有做了一個簡報然後上台分享，裡面寫得比較深，在這邊也分享一下：
https://hackmd.io/@OjHi9LEySUSS8jl6WKL4ug/HJZNNa0tc#/

---

## 參考資源

- [JavaScript 學演算法（二十二）- 遞迴 Recursion](https://chupai.github.io/posts/2008/alg_recursion/)
- [Javascript 的遞迴(Recursive)](https://medium.com/tomsnote/javascript%E7%9A%84%E9%81%9E%E8%BF%B4-recursive-f8ce5d084533)
- [mdn 遞迴](https://developer.mozilla.org/zh-TW/docs/Glossary/Recursion)
- [岔路上的風景 - 遞迴](https://ithelp.ithome.com.tw/articles/10265916)
- [JavaScript 演算法之遞迴](https://iter01.com/9337.html)
- [維基百科-費波那契數](https://zh.m.wikipedia.org/zh-tw/%E6%96%90%E6%B3%A2%E9%82%A3%E5%A5%91%E6%95%B0)
