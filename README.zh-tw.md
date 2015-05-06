# GitHub 不傳之秘
一些 Git 和 Github 好用但沒多少人知道的功能。
這不傳之秘的靈感來自於[Zach Holman](https://github.com/holman)在 2012 年的 Aloha Ruby會議上發表的[Git and GitHub Secrets](http://www.confreaks.com/videos/1229-aloharuby2012-git-and-github-secrets)([投影片](https://speakerdeck.com/holman/git-and-github-secrets))
以及他在 2013 年 WDCNZ 的演講 [More Git and GitHub Secrets](https://vimeo.com/72955426)([投影片](https://speakerdeck.com/holman/more-git-and-github-secrets))。

*短網址：[`http://git.io/sheet`](http://git.io/sheet)*

*閱讀其他語言： [English](README.md)、[한국어](README.ko.md)、[日本語](README.ja.md)、[简体中文](README.zh-cn.md) 和 [正體中文](README.zh-tw.md)。*

## 目錄
 - [GitHub](#github)
  - [忽略空白字符的比較](#忽略空白字符的比較)
  - [修正tab與空白字符](#修正tab與空白字符)
  - [查詢作者的提交記錄](#查詢作者的提交記錄)
  - [克隆倉庫](#克隆倉庫)
  - [分支](#分支)
    - [對某一個分支比較其他分支](#對某一個分支比較其他分支)
    - [Comparing Branches](#comparing-branches)
    - [Compare Branches across Forked Repositories](#compare-branches-across-forked-repositories)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [Keyboard Shortcuts](#keyboard-shortcuts)
  - [Line Highlighting in Repositories](#line-highlighting-in-repositories)
  - [Closing Issues via Commit Messages](#closing-issues-via-commit-messages)
  - [Cross-Link Issues](#cross-link-issues)
  - [Locking Conversations](#locking-conversations)
  - [CI Status on Pull Requests](#ci-status-on-pull-requests)
  - [Syntax Highlighting in Markdown Files](#syntax-highlighting-in-markdown-files)
  - [Emojis](#emojis)
  - [Images/GIFs](#imagesgifs)
    - [Embedding Images in GitHub Wiki](#embedding-images-in-github-wiki)
  - [Quick Quoting](#quick-quoting)
  - [Pasting Clipboard Image to Comments](#pasting-clipboard-image-to-comments)
  - [Quick Licensing](#quick-licensing)
  - [Task Lists](#task-lists)
    - [Task Lists in Markdown Documents](#task-lists-in-markdown-documents)
  - [Relative Links](#relative-links)
  - [Metadata and Plugin Support for GitHub Pages](#metadata-and-plugin-support-for-github-pages)
  - [Viewing YAML Metadata in your Documents](#viewing-yaml-metadata-in-your-documents)
  - [Rendering Tabular Data](#rendering-tabular-data)
  - [Revert a Pull Request](#revert-a-pull-request)
  - [Diffs](#diffs)
    - [Rendered Prose Diffs](#rendered-prose-diffs)
    - [Diffable Maps](#diffable-maps)
    - [Expanding Context in Diffs](#expanding-context-in-diffs)
    - [Diff or Patch of Pull Request](#diff-or-patch-of-pull-request)
    - [Rendering and diffing images](#rendering-and-diffing-images)
  - [Hub](#hub)
  - [Contributing Guidelines](#contributing-guidelines)
  - [Octicons](#octicons)
  - [GitHub Resources](#github-resources)
    - [GitHub Talks](#github-talks)
 - [Git](#git)
  - [Remove All Deleted Files from the Working Tree](#remove-all-deleted-files-from-the-working-tree)
  - [Previous Branch](#previous-branch)
  - [Stripspace](#stripspace)
  - [Checking out Pull Requests](#checking-out-pull-requests)
  - [Empty Commits](#empty-commits)
  - [Styled Git Status](#styled-git-status)
  - [Styled Git Log](#styled-git-log)
  - [Git Query](#git-query)
  - [Merged Branches](#merged-branches)
  - [Fixup and Autosquash](#fixup-and-autosquash)
  - [Web Server for Browsing Local Repositories](#web-server-for-browsing-local-repositories)
  - [Git Configurations](#git-configurations)
    - [Aliases](#aliases)
    - [Auto-Correct](#auto-correct)
    - [Color](#color)
  - [Git Resources](#git-resources)
    - [Git Books](#git-books)

## GitHub
### 忽略空白字符的比較
在任何比較網址後加上`?w=1`會移除所有空白字符的更動。如此可以使你更專注於程式碼的變更。

![Diff without whitespace](https://camo.githubusercontent.com/797184940defadec00393e6559b835358a863eeb/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f776869746573706163652e706e67)

[延伸閱讀：*Github的秘密*](https://github.com/blog/967-github-secrets)

### 修正tab與空白字符
在任何的比較網址或是檔案網址後加上`?ts=4`會把tab字元顯示成4個空白字符（預設是8個空白字符）。`ts=`後面的數字可以更改成你想要的長度。這項功能無法運用在Gists或是原始檔案視窗上。不過有套件（[Chrome](https://chrome.google.com/webstore/detail/github-tab-size/ofjbgncegkdemndciafljngjbdpfmbkn)或[Opera  extension](https://addons.opera.com/en/extensions/details/github-tab-size/)）可以運用。

這是Go原始碼，加上`?ts=4`前的樣子：

![Before, tab space example](http://i.imgur.com/GIT1Fr0.png)

...而這是加上`?ts=4`厚的樣子：

![After, tab space example](http://i.imgur.com/70FL4H9.png)

### 查詢作者的提交記錄
想要查詢某一個作者在這倉庫的提交記錄，在該網址後加上`?author={user}`。

```
https://github.com/rails/rails/commits/master?author=dhh
```

![DHH commit history](http://i.imgur.com/S7AE29b.png)

[延伸閱讀：*提交視窗之間的差異*](https://help.github.com/articles/differences-between-commit-views)

### 克隆倉庫
當克隆(clone)一個倉庫，最後面的`.git`可以被忽略。

```bash
$ git clone https://github.com/tiimgreen/github-cheat-sheet
```

[延伸閱讀：*Git `clone`指令*](http://git-scm.com/docs/git-clone)


###分支
#### 對某一個分支比較其他分支

如果你到倉庫的[分支](https://github.com/tiimgreen/github-cheat-sheet/branches)網頁，他就在提交按鈕的旁邊：

```
https://github.com/{user}/{repo}/branches
```

... 你會看到所有還沒有合併到主分支的分支列表。

從這裡你可以去看比較頁或是按下按鈕來刪除該分支。

![Compare branches not merged into master in rails/rails repo - https://github.com/rails/rails/branches](http://i.imgur.com/0FEe30z.png)

