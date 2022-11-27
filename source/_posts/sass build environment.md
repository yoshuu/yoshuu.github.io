---
title: 建立sass環境(2022)
date: 2022-11-27 14:01:27
tags:
  - sass
categories:
  - sass
---

此篇文章建立已經有 npm 的情況下。

如果是像我還有需要 node.js 的人，只要去安裝了 node.js，也會同時安裝 npm，至於如何安裝 node.js 可以去它的官網看=>https://nodejs.org/en/ 。

<!--more-->

回到這次主題。

## 環境分成兩種

- 全域的方式
- 本地端的方式

全域的方式代表只要裝了一次，整台電腦都會有 sass，而本地端則是範圍只限於一個專案之中，個人偏好使用本地端的方式，儘管可能每次都要裝一次，但會比較清楚使用了什麼。

## 全域安裝 sass 環境

第一步打開終端機。

第二步直接打指令。

安裝的指令： `npm install -g sass`
解除安裝的指令： `npm uninstall -g sass`

在這過程中可能會直接錯誤，畫面上會給出報醋，這是十分正常的，爬文後發現有一些權限問題，這時候只要最前面加上`sudo`，以及之後打上密碼就 ok 了。

例如：
安裝的指令 => `sudo npm install -g sass`
解除安裝的指令 => `sudo npm uninstall -g sass`

而要怎麼檢查安裝有沒有成功，或是有沒有成功卸載，可以透過查詢 sass 的版本來檢查，一樣在終端機的地方打上這段指令:`sass --version`。

要是你跟我一樣沒有在全域安裝的話就會出現這一段：
![](https://i.imgur.com/SK51ICe.png)

## 本地端安裝 sass 環境(自動編譯版)

在創立一個專案後，進入到裡面開始以下步驟。

1. 先 ` npm init -y`
   他跟 npm init 幾乎一樣，只是它會幫你把預設選項全部跳過，產生一個空白的 package.json (懶人專用)
   ![](https://i.imgur.com/vbB13xu.png)

2. 使用 `nam install sass`
   ![](https://i.imgur.com/Q5RzsZl.png)

3. 加上 ` "sass": "sass --watch scss/style.scss:style/style.css"`
   ![](https://i.imgur.com/0rN0iKz.jpg)

4. 把 scss 的資料夾給創出來

5. 成功編譯！
   之後之要寫`npm run sass`就可以一直幫忙自動編譯。
   ![](https://i.imgur.com/jeOJPkI.png)
