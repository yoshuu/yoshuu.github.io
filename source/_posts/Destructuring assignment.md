---
title: JavaScript 解構賦值解構什麼？
date: 2022-07-03 20:03:44
tags:
  - javascript
categories:
  - javascript
---

解構賦值是 es6 之後出來的一個新語法，我的理解它是一種語法糖，語法糖意思也就是說它可以用更簡單的方式達到相同的效果。

<!--more-->

至於它究竟解構了什麼？
其實就是陣列或是物件裡面的值，原本我們假如要取出陣列跟物件裡面的值，可能會這樣來寫：

```javascript=
let goodFruit = {
  name: '西瓜',
  color: 'green',
};

let name = goodFruit.name
let color = goodFruit.colo
```

但如果使用解構賦值的話，取用的方式就會變得稍微有些不同：

```javascript=
let goodFruit = {
  name: '西瓜',
  color: 'green',
};

let { name, color } = goodFruit

```

有看見兩者之間的差別了嗎？
下面的方式直接把取出的值骸需要再做宣告變數的步驟給取消了，直接就把物件裡面的值給取出來，一個步驟就把「宣告變數」及「變數賦值」的部分給完成。

而這種方式就可以減少很多代碼量，達到說優化可讀性的效果，另外除了物件以外，陣列也可以用解構賦值的方式：

```javascript=
//基本用法
const foo = ['one', 'two', 'three'];

const [A, B, C] = foo;
console.log(A);
console.log(B);
console.log(C);
```

## 小結

1. 解構賦值能夠減少很多重複性的事情，也能提高代碼整體的可讀性
2. 陣列跟物件的解構賦值取值順序不同，陣列是看索引值，物件則是屬性名稱
3. 除了順序之外陣列跟物件所用的括號也不一樣，一個是中括號，一個是大括號

## 參考資料

[https://eddy-chang.gitbook.io/javascript-start-from-es6/part4/destructuring](https://eddy-chang.gitbook.io/javascript-start-from-es6/part4/destructuring)

[https://www.casper.tw/javascript/2017/12/25/javascript-destructuring/](https://www.casper.tw/javascript/2017/12/25/javascript-destructuring/)

[https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#%E5%98%97%E8%A9%A6%E4%B8%80%E4%B8%8B](https://developer.mozilla.org/zh-TW/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment#%E5%98%97%E8%A9%A6%E4%B8%80%E4%B8%8B)

https://www.796t.com/article.php?id=288105
