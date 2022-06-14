---
title: javascript的throw用法
date: 2022-06-14 11:49:49
tags:
  - javascript
categories:
  - javascript
---

js 在拋出錯誤的時候會使用到 throw

提到`throw`之前要先來介紹一下相同性質的`try`, `catch`

<!--more-->

## try…catch

它會分成兩個區塊，一個 try 一個 catch

```javascript=
try {
    // 要執行的程式
} catch(error) {
    // ...
    // 錯誤發生時，上面的就不會執行，改執行這邊
}
```

舉例時間：

```javascript=
try {
  console.apple("apple不是正確的使用方式喔");
} catch (e) {
  console.log("我錯了");
}
```

這段 code 的結果會印出我錯了，如下：
![](https://i.imgur.com/8wTpx1D.png)

為什麼會發生這樣的結果？這是因為如果`try`區塊裡面的程式碼假如沒有任何的錯誤，就會直接忽略掉`catch`區塊裡面的程式碼，反之有錯的話，就會以`catch`裡面的程式碼為主，而錯誤的`try`就會中斷執行，所以在這個範例來說，因為`try`寫錯了，所以會以`try`裡面的程式碼為主

另外如果`catch`區塊如果接受了一個參數，就可以直接利用這個參數獲取錯誤資料，一般都會是直接在後台輸出資料，這邊來試試看：

```javascript=
try {
  console.apple("apple不是正確的使用方式喔");
} catch (e) {
  console.log("錯誤訊息 :", e);
}
```

這段 code 的結果會印出錯誤資訊，如下：
![](https://i.imgur.com/rqNUD5z.png)

## throw

接下來介紹這次的主題`throw`，它常常用於上面提到的`try…catch`結構，`throw`這個語句只要一出現就會直接中斷程式執行，代表說在它之後的語句都不會再被執行，簡單來說，在`try`的區塊時碰到`throw`就會直接中斷執行並且把控制權交給`catch`的區塊，所以說要是沒有`catch`的區塊，程式就會立刻停止

就如同最前面說的，`throw`可以拋出一個錯誤，這樣的好處是可以很清楚的知道說錯誤的具體位置，可以很方便去做判斷

舉例時間：

```javascript=
try {
  console.log("這邊很多蘋果，準備開始賣給顧客！");
  throw "等等有壞蘋果！終止交易！"; // throw 會中斷進行
  // 故意製造壞蘋果
  console.BadApple("壞蘋果x5");
  // 假如沒有被中斷，可以正常賣蘋果的世界線
  console.log("好吃蘋果，大賣特賣，大家快來買！");
} catch (e) {
  console.log(e);
  console.log("有壞蘋果不准你賣！");
}
```

這段 code 的結果順序會是

```javascript=
1. 這邊很多蘋果，準備開始賣給顧客！
2. 等等有壞蘋果！終止交易！
3. 有壞蘋果不准你賣！
```

如下：
![](https://i.imgur.com/dTgafCo.png)

首先，因為`throw`會中斷後面所有語句執行的特性，所以上面那段範例中還沒遇到`壞蘋果x5`就會直接跳到`catch`區塊的`有壞蘋果不准你賣！`，這邊我故意把`壞蘋果x5`弄成製造錯誤的方式，但是一樣被中斷跳過，於是可以發現一件事情：

> `throw`中斷了後面所有語句，包括了錯誤也一樣

所以這邊衍伸出了一個問題，如果錯誤是發生在`throw`語句之前，那會發生什麼事情呢，我們來試試看：

```javascript=
try {
  console.log("這邊很多蘋果，準備開始賣給顧客！");
  console.BadApple("壞蘋果x5");
  throw "等等有壞蘋果！終止交易！";
  console.log("好吃蘋果，大賣特賣，大家快來買！");
} catch (e) {
  console.log(e);
  console.log("有壞蘋果不准你賣！");
}

```

結果如下：
![](https://i.imgur.com/hep0E8x.png)

從結果可以發現說，假如錯誤發生在`throw`語句之前，那麼錯誤還是會被正常的顯示出來，而`throw`語句傳送的東西就不會出現，所以就可以利用像是這種模式，慢慢的交替把程式碼錯誤的位置給尋找出來

<br>

以上是我在學習`throw`時研究的紀錄，有任何問題都歡迎指教～

## 參考資料

1. [MDN try…catch](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/try...catch)
2. [MDN 流程控制與例外處理](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Guide/Control_flow_and_error_handling)
