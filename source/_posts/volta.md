---
title: volta 使用筆記
date: 2023-02-28 22:42:33
tags:
categories:
  - 還沒分類的
---

會學習 volta 主要是在進行 node 版本切換的時候，原本會是使用 nvm 的方式，但是聽說現在有一個更好用的工作叫做 volta，所以開始對這個工具進行研究。

<!--more-->

首先是 volta 的官網： https://volta.sh/

進到這個官網以後，就可以看得到如何安裝的方式。

![](https://i.imgur.com/zfHPEgR.png)

在這裡就打開終端機，然後下這串指令：

```
curl https://get.volta.sh | bash
```

就會自動安裝成功了，在這裡我自己有遇到一些問題，就是安裝明明是成功的，但是當我下`volta -v`試圖去查詢版本號時，卻得到`not found volta`的結果，讓我以為沒有成功安裝，但後來發現只是因為使用 vscode 內建的終端機去下載安裝完還需要重載不然不會正確顯示，其實原本還是有安裝，這點要記得注意。

## 如何使用

官網在這裡把 volta 的管理分成

1. Managing your toolchain
2. Managing your project

在這裡的第一個會使用到的指令是`volta install`

剛開一個新專案時都是空的，還沒有任何資料，這時候切換 node 版本的方式就只能是用`volta install`，我的理解是它有點類似於最外層的概念，但單獨講這塊可能會難想像，所以先繼續往下。

假如在這個空的資料夾裡面再創兩個新的 project，
像是有一個叫做"0221"的資料夾，裡面創了兩個 vue 的新專案(vue-project , vue-project2)

![](https://i.imgur.com/QR4pSXl.png)

會發現裡面的 project 打開後，還會有`package.json`，而最外層沒有，而如何改動這個 vue 的新專案的 node 版本就會需要用到`volta pin`指令

在這邊實際實作一次：

先檢查外層"0221"的 node 版本狀況
![](https://i.imgur.com/T2nboCv.png)

然後進到"vue-project"裡，
這邊使用`volta pin`指令來改變 node 版本

下`volta pin node@15`，
會跳出訊息
`success: pinned node@15.14.0 (with npm@7.7.6) in package.json`
代表已經成功轉換了，這時候去看"vue-project"的`package.json`會發現已經被添加了 volta 相關版本訊息

![](https://i.imgur.com/v31NaO7.png)

這時候已經轉換成功了，所以去看 node 版本會發現已經變成 15
![](https://i.imgur.com/B9XHVDY.png)

而這時候再使用`volta install`系列就改變不了"vue-project"的 node 版本，因為有`package.json`會優先看這裡的。

轉換到"vue-project2"的資料夾，會發現版本還是處在外層"0221"的 node 版本狀況，然後再用`volta pin`指令來改變 node 版本，成功後這三種地方的 node 版本就都會不一樣

![](https://i.imgur.com/uPptGaP.png)

## 重點理解整理

一般來說`volta install`可以理解成是改變預設狀態下的 node 版本，而`volta pin`則是會把改變的 node 版本給紀錄在`package.json`，所以會有固定的效果，只要是在那個`package.json`範圍的都會吃到它當中的 node 版本。

在這邊就會產生一些優先權問題，這些都是正常的：

1. 使用`volta pin`後，`volta install`會失效
2. 沒有`package.json`就沒辦法使用`volta pin`

目前體感的好處是，假如協作的對象也有使用`volta`，那可以從他的專案的`package.json`去看 node 的版本，這點很方便，切換的速度也十分的快速，想切換就切換～！

最後以上介紹的是普通狀況會常用的兩個指令，另外還有許多的指令這部分可以參考官網：
![](https://i.imgur.com/oc2BSKw.png)

官網的地方：https://docs.volta.sh/reference/
