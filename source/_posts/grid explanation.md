---
title: "grid的不同解讀"
date: 2022-05-19 11:38:57
tags:
  - grid
categories:
  - css
---

繼 css flex 佈局出來之後，後來又出現了 css grid 的佈局方式，不過 grid 這個詞不是被新發明出來的，是之前就有的東西。

<!--more-->

假如你想跟別人討論說要使用 grid，但沒講清楚是哪種「grid」的話，可能溝通上就會造成許多問題，這篇會提到有三種解讀方式：

## 格線系統(grid system)的 grid

一種 ui 設計會使用到的概念，可以幫助設計師更好的在畫面上安排，另外前端框架 Bootstrap 也會使用到 grid system，這邊要注意到並不是指 css 裡面的那個 grid

## css 佈局方式的 grid

屬於 css 裡面的佈局方式，使用時 display 會先變成 grid，如：

```
display:grid
```

使用之後，這個使用的區塊元素就都會變成「grid」，只需再搭配一堆 grid 系列的語法，就能利用 gird 讓網頁排成自己想要的形狀～

## 簡寫屬性的 grid

剛剛上面提到，把區塊設成「grid」物件後，就能利用一堆的 gird 系列語法來完成佈局，這邊提到的簡寫屬性的 grid 就是它裡面的其中一種寫法，如：

```
grid: auto-flow / 1fr 1fr 1fr;
grid: auto-flow dense / 40px 40px 1fr;
grid: repeat(3, 80px) / auto-flow;
```

## 小結

一個 grid 各種解讀，蠻容易搞混的，就像我當初學習 Bootstrap 以為它的 grid system 主要是用 css 的 grid，但是並沒有，反而還跟 css 的 flex 相關度比較大。
