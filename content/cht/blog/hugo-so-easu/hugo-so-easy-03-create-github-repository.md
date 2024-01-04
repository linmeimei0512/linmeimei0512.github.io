---
author: Meimei
title: HUGO So Easy (3) - 建立 GitHub Repository
date: 2023-12-12
description: How to create a repository on GitHub
tags:
  - hugo
keywords:
  - hugo
thumbnail: /images/hugo/hugo.png
---
## 建立 GitHub Repository

開啟你的 Github 首頁，點擊右上角的 ➕，並且選擇 `New Repository`
<center><img src="/images/hugo/03-create-github-repository/create-01-new-repository.png" width="50%"/></center>


這時候要想一個 `Name`，這個 `Name` 可以和網站有關聯又或是自己開心都可以，如果輸入合法且可使用，下方會顯示 `{Name} is available.` 綠色的字樣
<center><img src="/images/hugo/03-create-github-repository/create-02-name.png" width="70%"/></center>


權限選擇公開 `Public`
<center><img src="/images/hugo/03-create-github-repository/create-03-public.png" width="50%"/></center>


最後按下 `Create repository`
<center><img src="/images/hugo/03-create-github-repository/create-04-create.png" width="70%"/></center>


<br>

## Clone GitHub Repository 到本地端

剛剛新建的 `Repository` 頁面，找到 `Quick setup` ，然後按下最右邊的複製按鈕，把 git clone 的路徑複製下來
<center><img src="/images/hugo/03-create-github-repository/create-05-git-url.png" width="100%"/></center>


開啟檔案總管，如果是 `mac` 就開啟 `Finder` ，找一個風水寶地的資料夾，這邊我是新增一個叫 `Github Blog` 資料夾
<center><img src="/images/hugo/03-create-github-repository/create-06-new-folder.png" width="100%"/></center>


接著開啟 Windows 叫做 `命令提示字元 (CMD)` 又或是叫 `PowerShell` ，而 mac / Linux 叫 `終端機 (Terminal)` 的東西。然後先輸入 `cd` 在把剛剛選定的風水寶地資料夾拉進去 Termainl 之中。簡單來說就是要讓 Terminal 指到那個風水寶地資料夾
<center><img src="/images/hugo/03-create-github-repository/create-07-cd-folder.png" width="70%"/></center>


先輸入 `git clone` 然後再把剛剛在 Github 上複製的 git clone 路徑貼上，然後按下 `Enter`
<center><img src="/images/hugo/03-create-github-repository/create-08-clone.png" width="100%"/></center>


回到檔案總管 `Finder`，就會看到把剛剛在 GitHub 上建立的 `Repository` 給 clone 下來了
<center><img src="/images/hugo/03-create-github-repository/create-09-local-folder.png" width="100%"/></center>

