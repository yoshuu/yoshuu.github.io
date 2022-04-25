---
title: "什麼時候會用img , 什麼時候會用background-image"
date: 2022-03-26T01:01:00.002-07:00
tags:

categories:
  - 舊部落格移植文章
---

原文連結: https://appcs342.blogspot.com/2022/03/img-background-image.html
移植時的最後更新日期: 2022-03-26T01:01:42.352-07:00

<p>一個是html標籤的img，一個是css的background-image，兩個都能讓網頁中顯示出圖片。</p><p>我自己目前個人遇到的狀況會使用img &gt; background-image 。</p><p><br /></p><h2 style="text-align: left;"><span style="font-size: large;"><b>img:</b></span></h2><p>會使用img的情況通常是：</p><p></p><ul style="text-align: left;"><li>網頁不只是需要單純的一張圖片而已，還需要像是超連結的功能，或是想讓圖片能夠縮小放大。</li><li>有需要使用動畫的時候，因為img的動畫表現會比background-image更好。</li><li>影印頁面時，圖片也想跟著被印出來。<br /><br /></li></ul><p></p><h2 style="text-align: left;"><span>&nbsp;</span>background-image:</h2><div>簡單來說，是像是網頁中當背景圖片的感覺，意味著background-image其實並沒有自己本身的意義存在，它沒有辦法去代表網頁中內容的任何事情。<br /><br /></div><div>會使用的狀況：</div><div><ul style="text-align: left;"><li>圖片不是內容的一部分（設計考量）。<br /></li><li>網頁需要有圖片當背景。<br /></li><li>影印頁面時，圖片不想跟著被印出來。<br /><br /><br /></li></ul><h2 style="text-align: left;">小結：</h2></div><div>img是屬於頁面內容的一部分，它是擁有含義的圖片。<br />background-image則是不屬於頁面內容的一部分，它是沒有含義，可以拿來單純當作背景的圖片。<br /></div>
