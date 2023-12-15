---
author: Meimei
title: HUGO So Easy (8) - 導入 Giscus 留言系統
date: 2023-12-13
description: How to add giscus comment system to HUGO.
tags:
  - hugo
thumbnail: /hugo.svg
---
## 開啟 GitHub Discussions 功能

開啟存放 HUGO 的 GitHub，點擊上方列表的 `⚙ Settings`，並往下找到 `Discussions` 然後把它勾選起來
<center><img src="/images/hugo/08-add-giscus/giscus-01-enable-discussions.png" width="100%"/></center>

開啟 `Discussions` 後，在上方列表會看到出現了 `Discussions`
<center><img src="/images/hugo/08-add-giscus/giscus-02-discussions.png" width="100%"/></center>

</br>


## 在 GitHub 上安裝 Giscus App

進到安裝頁面 [https://github.com/apps/giscus](https://github.com/apps/giscus) 點擊右邊的 `Install`
<center><img src="/images/hugo/08-add-giscus/giscus-03-giscus-install.png" width="100%"/></center>

選 `Only select repositories`，然後點選 `Select repositories`，最後選擇 HUGO 所在的 repository
<center><img src="/images/hugo/08-add-giscus/giscus-04-select-repository.png" width="60%"/></center>

確定 HUGO 所在的 repository 有被選擇後就按下 `Install`
<center><img src="/images/hugo/08-add-giscus/giscus-05-repository-install.png" width="60%"/></center>

</br>


## 產生 Giscus 配置文件

先去 [https://giscus.app/](https://giscus.app/) 生成配置參數，裡面有蠻多東西可以設定的，但是為了示範我只標示出必要更動的參數
- 儲存庫 (Repository Name)  
  將自己 GitHub 的 Username 加上剛剛打開 Discussions 功能的 Repository Name 甜到儲存庫欄位中，格式如下
  ```bash
  my-username/my-repository-name
  ```
<center><img src="/images/hugo/08-add-giscus/giscus-06-repository-name.png" width="90%"/></center>

- Discussion 分類  
  這邊分類不一定要跟我一樣選 `Annoumcements`，不過如果不知道要選什麼就先跟我一樣吧
<center><img src="/images/hugo/08-add-giscus/giscus-07-category.png" width="90%"/></center>

填完之後拉到下面，會看到自動產生 `script` 文件
<center><img src="/images/hugo/08-add-giscus/giscus-08-script.png" width="100%"/></center>

</br>


## 在 HUGO 加入 Giscus

每個主題要加入 Giscus 的方式都不盡相同，這邊我以 PaperMod 主題來示範  
開啟 `config.yml`，找到 `comments` 設定
<center><img src="/images/hugo/08-add-giscus/giscus-09-config-comments.png" width="70%"/></center>
如果預設是 `false`，請先改成 `true`

接著把下方參數複製到 `comments` 下面，記得要把 `repo`、`repoId`、`category`、`categoryId` 從剛剛的 script 複製過來

```yaml
  commentsParams:
    repo: [ENTER REPO HERE]
    repoId: [ENTER REPO ID HERE]
    category: [ENTER CATEGORY NAME HERE]
    categoryId: [ENTER CATEGORY ID HERE]
    mapping: title
    reactionsEnabled: 1
    emitMetadata: 1
    inputPosition: top
    lang: zh-TW
```

貼上後如下：
<center><img src="/images/hugo/08-add-giscus/giscus-10-config-comments-parameter.png" width="70%"/></center>

在 HUGO repository 根目錄開啟 Terminal
<center><img src="/images/hugo/08-add-giscus/giscus-11-root-path.png" width="100%"/></center>

在 `layout` 建立一個 `partials` 資料夾

```bash
mkdir layouts/partials 
```
<center><img src="/images/hugo/08-add-giscus/giscus-12-mkdir.png" width="100%"/></center>

將 `themes/PaperMod/layouts/partials/comments.html` 和 `themes/PaperMod/layouts/partials/footer.html` 複製到剛剛建立的 `layouts/partials` 資料夾內

```bash
cp themes/PaperMod/layouts/partials/comments.html layouts/partials/comments.html
cp themes/PaperMod/layouts/partials/footer.html layouts/partials/footer.html
```
<center><img src="/images/hugo/08-add-giscus/giscus-13-cp.png" width="100%"/></center>

將下方 `javascript` 程式碼複製到 `comments.html` 內

```jsx
<div class="comments">
    <script>
    function loadComment() {
        let theme = localStorage.getItem('pref-theme') === 'dark' ? 'transparent_dark' : 'light';
        let s = document.createElement('script');
        s.src = '<https://giscus.app/client.js>';
        s.setAttribute('data-repo', '{{- site.Params.commentsParams.repo -}}');
        s.setAttribute('data-repo-id', '{{- site.Params.commentsParams.repoId -}}');
        s.setAttribute('data-category', '{{- site.Params.commentsParams.category -}}');
        s.setAttribute('data-category-id', '{{- site.Params.commentsParams.categoryId -}}');
        s.setAttribute('data-mapping', '{{- site.Params.commentsParams.mapping -}}');
        s.setAttribute('data-reactions-enabled', '{{- site.Params.commentsParams.reactionsEnabled -}}');
        s.setAttribute('data-emit-metadata', '{{- site.Params.commentsParams.emitMetadata -}}');
        s.setAttribute('data-input-position', '{{- site.Params.commentsParams.inputPosition -}}');
        s.setAttribute('data-lang', '{{- site.Params.commentsParams.lang -}}');
        s.setAttribute('data-theme', theme);
        s.setAttribute('crossorigin', 'anonymous');
        s.setAttribute('async', '');
        document.querySelector('div.comments').innerHTML = '';
        document.querySelector('div.comments').appendChild(s);
    }
    loadComment();
    </script>
</div>
```
<center><img src="/images/hugo/08-add-giscus/giscus-14-comments-html.png" width="100%"/></center>

到這邊我們就在 HUGO 成功導入 `Giscus` 留言系統嚕