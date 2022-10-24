---
title: HTML 內建範本的三個meta
date: 2022-10-24 09:37:10
tags:
  - html
categories:
  - html
---

創建完.html 的檔案後，在開始把版面切出來之前，通常會使用!的方式把內建的範本給建立出來，使用內建範本會把一些基本的東西都先呈現出來，像是 html、head、body 的 tag。

<!--more-->

![](https://i.imgur.com/Nm0Ll9g.png)

雖然十分的理所當然，但也因為方便所以有時會忽略掉那些內建的東西是什麼，在內建範本之中，我覺得最容易被忽略掉，跟最容易經過時間遺忘的是其中的三個 meta tag，所以在此做個筆記讓之後遺忘可以複習。

![](https://i.imgur.com/Zu9pEFi.png)

## <meta charset="UTF-8">

這一段是跟編碼有所關聯，可以用來指定說這個網頁內容需要用什麼編碼。

一般來說會使用"UTF-8"來做編碼，HTML5 的規範也推薦所有開發人員都使用 UTF-8 字符集，因為它幾乎涵蓋了世界上所有的字符跟符號。

詳細可以參考這一篇文章，我覺得還不錯：
[[HTML][新手] 04. 中文編碼表示 meta charset](https://progressbar.tw/posts/200)

## <meta http-equiv="X-UA-Compatible" content="IE=edge">

這一段主要是用到控制 IE 相容模式，可以用此來設定 IE 的版本。

讓在 IE 瀏覽器的時候，也能正常地觀看網頁，但現在因為 IE 已漸漸沒落，所以感覺這段的作用慢慢減少中，之後可能就會完全停用。

關於這塊的文章：
[IE 相容模式設定 X-UA-Compatible](https://hackercat.org/web-notes/ie-x-ua-compatible)
[<meta http-equiv="X-UA-Compatible" content="IE=edge">詳解](https://www.cnblogs.com/youpeng/p/10991144.html)

## <meta name="viewport" content="width=device-width, initial-scale=1.0">

這段的作用是 rwd 響應式的設定，會需要 meta 裡面的 viewport 來指定瀏覽器怎麼渲染和縮放網頁畫面的的大小。

比較詳細的語法介紹：
[html viewport meta 淺見及說明](https://www.fooish.com/html/meta-viewport.html)
