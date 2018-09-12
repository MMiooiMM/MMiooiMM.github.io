---
layout: post
title:  "使用 jekyll + Github 來建立一個部落格"
date:   2018-09-10 14:33:38 +0800
tags: [jekyll, Github]
---

使用 jekyll + Github 來建立一個部落格。

這邊會大致介紹如何操作。(以下操作指令都在終端機進行)

### 安裝 jekyll

jekyll 是基於 ruby 語言寫的，所以要使用前須先安裝 [ruby][ruby-download]，之後才可以操作 gem 指令(類似 npm 的套件吧)。

安裝 jekyll `gem install jekyll`

除了安裝 jekyll 之外，也需要一併安裝 rake 與 bundle 才能正確安裝。

`gem install rake` `gem install bundle`

這部分我也不懂，我沒學過 ruby。

然後就能進行 jekyll 的範本下載了

`jekyll new .` 指令中的 . 可以替換成檔案名稱，在目標目錄裡開一個新資料夾並放入範本，不加就是直接在目標目錄建立範本。

如果在上述指令有新增資料夾，請執行 `cd foldername` 將 foldername 替換成你的名稱，將目標目錄移動到該資料夾。

`jekyll server` 便能執行 jekyll 來看一下目前的網站。

### 操作 jekyll

jekyll 是由 markdown 文件來編寫 html，這對我來說撰寫文章比較方便也好看。

在Jekyll中，資料夾架構如下：

```
my-awesome-site
|-- _drafts     草稿資料夾
|-- _layouts    模版資料夾
|-- _plugins    外掛資料夾
|-- _posts      文章資料夾
|-- _site       靜態網頁轉換存放處
|-- _config.yaml   網站設定檔
```

新增文章只需要把 markdown 檔放到`_posts`就可以了。

不過必須遵守年-月-份-文章網址名稱(需英文).md的檔名規範才行，不然會失效喔。

除此之外，還需要去 _config.yml 設定你的相關資訊，改成自己的唷。

### 上傳到自己的Github

首先到自己的 Github 新增一個 account.github.io 的專案，將 account 改成你的帳號。

建立後將本來完成的 jekyll 資料夾，執行 git 指令。

`git init` 在目標目錄的資料夾底下建立 git 版本控管

`git add .` 因為在建立 jekyll 專案時已經加入 .gitignore 檔案，不用一一挑除。

`git commit -m "你要的資訊"` 進行一次 commit ，沒有 commit 過的專案無法執行 push 指令。

`git remote add origin https://github.com/account/account.github.io.git` 將 account 替換成你的帳號，或者直接複製在 github 上面的訊息，已設定遠端分支。

`git push -u origin master` 將本地分支推送到遠端分支，執行時會顯示失敗，並要求輸入帳號密碼，完成後即可上傳。

上傳後便可以在 account.github.io 看到自己的 blog 了。

參考連結
<br>[利用Jekyll與Github Page建立自己的Dev-Blog][jekyll-GithubPage]
<br>[Jekyll 介紹][what-is-jekyll]

[ruby-download]: https://www.ruby-lang.org/zh_tw/downloads/
[jekyll-GithubPage]: https://3kni.com/2016/make-own-blog-with-jekyll-and-github-page/
[what-is-jekyll]: https://wcc723.github.io/jekyll/2014/01/04/what-is-jekyll/
