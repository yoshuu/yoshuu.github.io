---
title: node.js 取得使用者輸入
date: 2022-11-29 09:18:35
tags:
  - javascript
categories:
  - javascript
---

- 自己研究時的參考資源： -[在 JavaScript 中獲取使用者輸入| D 棧](https://www.delftstack.com/zh-tw/howto/javascript/get-user-input-in-javascript/)
  [Hans-Tsai/Node.js-Learn](https://github.com/Hans-Tsai/Node.js-Learn) -[Node.js 官網](https://nodejs.org/en/)
  node.js 要取得使用者輸入會需要方法，我目前在使用的方式是用 readline 的方式，可以藉由它直接去做到使用者輸入

<!--more-->

## 主要的幾種方式

- readline => node.js 提供，可直接引用來幫助取得輸出輸入
- prompt-sync =>

|      | readline   | prompt-sync |
| ---- | ---------- | ----------- |
| Text | 非同步     | 同步        |
| Text | 不需要安裝 | 需要安裝    |

## readline

引用基於 callback and sync 的 API

```
const readline = require('node:readline');
```

引用基於 promise 的 API

```
import * as readline from 'node:readline/promises';
```

CJS 範例版本 => commonJs

```javascript=
const readline = require('node:readline');
const { stdin: input, stdout: output } = require('node:process');

const rl = readline.createInterface({ input, output });

rl.question('What do you think of Node.js? ', (answer) => {
  // TODO: Log the answer in a database
  console.log(`Thank you for your valuable feedback: ${answer}`);

  rl.close();
});
```

ESM 範例版本 => ES module

```javascript=
import * as readline from 'node:readline/promises';
import { stdin as input, stdout as output } from 'node:process';

const rl = readline.createInterface({ input, output });

const answer = await rl.question('What do you think of Node.js? ');

console.log(`Thank you for your valuable feedback: ${answer}`);

rl.close();
```

## prompt-sync

首先，你需要使用 NPM 或 Yarn 安裝 prompt-sync

```
npm install prompt-sync
```

```
yarn add prompt-sync
```

CJS 範例版本 => commonJs

```javascript=
const prompt = require("prompt-sync")();

const name = prompt("你叫做什麼名字?");
console.log(`您好 ${name}`);

```
