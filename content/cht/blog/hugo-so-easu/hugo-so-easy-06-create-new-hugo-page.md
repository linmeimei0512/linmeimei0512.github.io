---
author: Meimei
title: HUGO So Easy (6) - 建立新的 HUGO 頁面
date: 2023-12-12
description: How to create a new HUGO page
tags:
  - hugo
keywords:
  - hugo
thumbnail: /images/hugo/hugo.png
---
## 建立 HUGO 新頁面
再次回到 `根目錄`
<center><img src="/images/hugo/06-create-new-page/new-page-01-root-path.png" width="100%"/></center>

建立一個叫 `my-first-post` 的頁面
```bash
hugo new posts/my-first-post.md
```
<center><img src="/images/hugo/06-create-new-page/new-page-02-first-post.png" width="100%"/></center>

HUGO 會在 `content/posts/` 目錄下建立一個叫 `my-first-post.md` 的檔案
<center><img src="/images/hugo/06-create-new-page/new-page-03-first-post-folder.png" width="100%"/></center>

開啟 `my-first-post.md` 這個檔案，把 `draft = true` 改成 `draft = false`，然後將下面的內容複製到檔案內 (這些是頁面的範例文字)，然後存欓
```markdown
## Introduction

This is **bold** text, and this is *emphasized* text.

Visit the [Hugo](<https://gohugo.io>) website!
```

這時候可以再啟動一次 HUGO 就會看到網站有東西嚕!
```bash
hugo server -D
```
<center><img src="/images/hugo/06-create-new-page/new-page-04-web.png" width="100%"/></center>
