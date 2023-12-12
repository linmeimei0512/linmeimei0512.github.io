---
author: Meimei
title: HUGO So Easy (4) - 建立 HUGO 網站
date: 2023-12-12
description: How to create a new HUGO
tags:
  - hugo
thumbnail: /hugo.svg
---
## 建立新的 HUGO 網站
剛剛我們已經建立了一個存放網站的空間，現在要開始建立網站了  
建立 HUGO 網站的指令如下：
```Bash
hugo new site {Site Name} --force
```

這邊我要在剛剛 clone 下來的 Repository 建立新的 `HUGO Site`，因此這邊我的 `Site Name` 會填 `Repository Name`。這邊要注意，終端機 Terminal 要在 Repository 的上一層目錄
```Bash
hugo new site hugo-example --force
```
<center><img src="/images/hugo/04-create-hugo/create-01-create-hugo.png" width="100%"/></center>

這樣我們其實就建立好一個 HUGO 框架的網站了，是不是超級快速的  
只是現在這個網站裡面並沒有任何內容

</br>

## 在本地端啟動 HUGO 網站預覽
先利用 `cd` 進到 `Repository folder` (下方『根目錄』代表 hugo-example 這個目錄資料夾)
```Bash
cd hugo-example
```

接著我們可以輸入
```Bash
hugo server -D
```
<center><img src="/images/hugo/04-create-hugo/create-02-hugo-server.png" width="100%"/></center>

在本地端啟動 HUGO 網頁，如果有看到 [http://localhost:1313/](http://localhost:1313/) 就代表起動成功嚕！  
這時候我們就可以開心的利用瀏覽器開啟預設網址 [http://localhost:1313/](http://localhost:1313/) 啦！
<center><img src="/images/hugo/04-create-hugo/create-03-page-not.png" width="100%"/></center>

但是相信大家看到的畫面會是如下，心頓時碎滿地….   
這是因為我們網頁裡面沒有任何東西，也沒有設定起始頁面，當然就顯示 `Page Not Found` 給你看嚕！  
這時候我們可以先按下 `Ctrl + C` 來結束。