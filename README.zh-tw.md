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
    - [比較分支](#比較分支)
    - [比較同一來源但不同倉庫的分支](#比較同一來源但不同倉庫的分支)
  - [Gists](#gists)
  - [Git.io](#gitio)
  - [快捷鍵](#快捷鍵)
  - [強調列](#強調列)
  - [透過提交訊息來關掉事項](#透過提交訊息來關掉事項)
  - [事項連結](#事項連結)
  - [鎖定討論](#鎖定討論)
  - [Pull Request的CI狀態](#Pull Request的CI狀態)
  - [Markdown的高亮語法](#Markdown的高亮語法)
  - [表情符號](#表情符號)
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

#### 比較分支
若想要用GitHub來比較分之，只要把網址改成這樣：

```
https://github.com/{user}/{repo}/compare/{range}
```

其中，`{range}`可以是`master...4-1-stable`，意思是比較`master`分支與`4-1-stable`分支。

比方說：

```
https://github.com/rails/rails/compare/master...4-1-stable
```

![Rails branch compare example](http://i.imgur.com/tIRCOsK.png)

`{range}` 也可以改成像這樣：

```
https://github.com/rails/rails/compare/master@{1.day.ago}...master
https://github.com/rails/rails/compare/master@{2014-10-04}...master
```

*日期的格式是`YYYY-MM-DD`*

![Another compare example](http://i.imgur.com/5dtzESz.png)

分支也可以在比較視窗和更新視窗中使用：

```
https://github.com/rails/rails/compare/master...4-1-stable.diff
https://github.com/rails/rails/compare/master...4-1-stable.patch
```

[延伸閱讀：*比較不同時間的提交*](https://help.github.com/articles/comparing-commits-across-time)

#### 比較同一來源但不同倉庫的分支
若要比較同一來源但不同倉庫的分支，把網址改成如下：

```
https://github.com/{user}/{repo}/compare/{foreign-user}:{branch}...{own-branch}
```

For example:

```
https://github.com/rails/rails/compare/byroot:master...master
```

![Forked branch compare](http://i.imgur.com/Q1W6qcB.png)

### Gists
[Gists](https://gist.github.com/)是一種很輕鬆的方式存放部份原始碼的工具，而且不需要建立任何倉庫。

![Gist](http://i.imgur.com/VkKI1LC.png?1)

另外，在任何Gist網址結尾處加上`.pibb`（[範例](https://gist.github.com/tiimgreen/10545817.pibb)）可以取得*只限網頁*的版本，這樣就可以內嵌再任何其他網站上。

Gists可以被當城市倉庫，所以他們也可以被克隆。

```bash
$ git clone https://gist.github.com/tiimgreen/10545817
```

![Gists](http://i.imgur.com/BcFzabp.png)

這代表，你可以座任何修改並上傳到Gists上：

```bash
$ git commit
$ git push
Username for 'https://gist.github.com': 
Password for 'https://tiimgreen@gist.github.com': 
```

但是，Gists並沒有支援目錄。所有的檔案必須要在倉庫的根節點上。
[延伸閱讀：*建立Gists*](https://help.github.com/articles/creating-gists)

### Git.io
[Git.io](http://git.io)是Github的短網址。

![Git.io](http://i.imgur.com/6JUfbcG.png?1)

你可以透過純HTTP的方式，像是Curl，來使用：

```bash
$ curl -i http://git.io -F "url=https://github.com/..."
HTTP/1.1 201 Created
Location: http://git.io/abc123

$ curl -i http://git.io/abc123
HTTP/1.1 302 Found
Location: https://github.com/...
```

[延伸閱讀：*Git.io.*](https://github.com/blog/985-git-io-github-url-shortener)

### 快捷鍵
在任一個倉庫頁面上，快捷鍵讓你可以方便導覽。

 - 按鍵`t`會帶出檔案列表。
 - 按鍵`w`會帶出分支選擇器。
 - 按鍵`s`會顯示當前倉庫的搜尋欄。此時按下倒退鍵就會切換到搜尋整個Github。
 - 按鍵`l`用來編輯已存在事件的標籤。
 - 按鍵 `y` **當查看文件時** (比方說：`https://github.com/tiimgreen/github-cheat-sheet/blob/master/README.md`)會產生快照。即使原始碼被改變了，你依然可以看得到現在你看到的東西。

瞭解在這葉面上的所有快捷鍵，可以按下`?`：

![Keyboard shortcuts](http://i.imgur.com/y5ZfNEm.png)

[延伸閱讀：搜尋語法](https://help.github.com/articles/search-syntax/)

### 強調列
在原始碼檔案網址結果加上`#L52`或是簡單的點選列號都會強調該列。

這也可以使用範圍，像是`#L53-L60`，用點選方式則用`shift`來點選那兩行：

```
https://github.com/rails/rails/blob/master/activemodel/lib/active_model.rb#L53-L60
```

![Line Highlighting](http://i.imgur.com/8AhjrCz.png)

### 透過提交訊息來關掉事項
如果一個特別的提交修訂了一個事項，則在事項號碼前面有以下關鍵字（`fix/fixes/fixed`, `close/closes/closed` 或 `resolve/resolves/resolved`），則一旦這個提交到主分支上，該事項會被關掉。

```bash
$ git commit -m "Fix screwup, fixes #12"
```

這個會關掉這個事項並會參考到這次提交。

![Closing Repo](http://i.imgur.com/Uh1gZdx.png)

[延伸閱讀：*透過提交關掉事項*](https://help.github.com/articles/closing-issues-via-commit-messages)

### Issue連結
若你想要連結到同倉庫的其他Issue，只要用`#`後面帶上Issue號碼，Github就會幫你自動連結。

若要連結到其他倉庫的Issue，則使用`{user}/{repo}#ISSUE_NUMBER`。像是： `tiimgreen/toc#12`。

![Cross-Link Issues](https://camo.githubusercontent.com/447e39ab8d96b553cadc8d31799100190df230a8/68747470733a2f2f6769746875622d696d616765732e73332e616d617a6f6e6177732e636f6d2f626c6f672f323031312f736563726574732f7265666572656e6365732e706e67)

### 鎖定討論

Pull Request和Issue現在可以被該倉庫的擁有者或是共事者給鎖定。

![Lock conversation](https://cloud.githubusercontent.com/assets/2723/3221693/bf54dd44-f00d-11e3-8eb6-bb51e825bc2c.png)

這代表不是這專案的共事者將無法評論這個項目。

![Comments locked](https://cloud.githubusercontent.com/assets/2723/3221775/d6e513b0-f00e-11e3-9721-2131cb37c906.png)

[延伸閱讀：*鎖定對話*](https://github.com/blog/1847-locking-conversations)

### Pull Request的CI狀態
如果設置正確，每次你收到Pull Request，[Travis CI](https://travis-ci.org/) 會自動執行建構，就像每次提交一樣。
瞭解更多，請參考[Travis CI入門](http://docs.travis-ci.com/user/getting-started/)。

[![Travis CI status](https://cloud.githubusercontent.com/assets/1687642/2700187/3a88838c-c410-11e3-9a46-e65e2a0458cd.png)](https://github.com/octokit/octokit.rb/pull/452)

[延伸閱讀：*提交狀態API*](https://github.com/blog/1227-commit-status-api)

### Markdown的高亮語法
比方說，要高亮Ruby原始碼在Markdown檔案中，要寫成：

    ```ruby
    require 'tabbit'
    table = Tabbit.new('Name', 'Email')
    table.add_row('Tim Green', 'tiimgreen@gmail.com')
    puts table.to_s
    ```

這會產生：

```ruby
require 'tabbit'
table = Tabbit.new('Name', 'Email')
table.add_row('Tim Green', 'tiimgreen@gmail.com')
puts table.to_s
```

GitHub使用[Linguist](https://github.com/github/linguist)來執行語言徵測與語法高亮。若要知道哪些關鍵字是合法的，請詳閱[languages YAML file](https://github.com/github/linguist/blob/master/lib/linguist/languages.yml)。

[延伸閱讀：*GitHub 喜歡 Markdown.*](https://help.github.com/articles/github-flavored-markdown)

### 表情符號
表情符號可以使用在Pull Request、Issues、提交訊息、倉庫描述等等，使用 `:name_of_emoji:`。

詳盡的表情符號列表可以在[emoji-cheat-sheet.com](http://www.emoji-cheat-sheet.com/) 或 [scotch-io/All-Github-Emoji-Icons](https://github.com/scotch-io/All-Github-Emoji-Icons)找到。

最常被使用的是：
1. `:shipit:`
2. `:sparkles:`
3. `:-1:`
4. `:+1:`
5. `:clap:`

