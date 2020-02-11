# 貢獻指南

<!-- TOC -->
*WE PROVIDE ENGLISH VERSION, PLEASE CLICK [HERE](https://github.com/wuhan2020/wuhan2020/blob/master/CONTRIBUTING_EN.md)*

- [貢獻指南](#貢獻指南)
  - [我要提交數據資訊](#我要提交數據資訊)
  - [我要提 ISSUE，提 PR](#我要提-issue提-pr)
    - [0、提交 issue](#0提交-issue)
    - [1、認領任務](#1認領任務)
    - [2、Fork 本倉庫](#2fork-本倉庫)
    - [3、Clone 倉庫](#3clone-倉庫)
    - [4、新建 `branch`](#4建立-branch)
    - [5、修改內容，並提交](#5修改內容並提交)
    - [6、同步上游倉庫變更](#6同步上游倉庫變更)
    - [7、推送新分支到自己的遠端倉庫](#7推送新分支到自己的遠端倉庫)
    - [8、提 `Pull Request`](#8提-pull-request)
    - [9、如果你的代碼合併時出現衝突時，你可以：](#9如果你的代碼合併時出現衝突時你可以)
    - [10、當你的代碼被合併進去以後，你可以：](#10當你的代碼被合併進去以後你可以)
  - [項目機器人說明](#項目機器人說明)
  - [Slack 交流群組](#slack-交流群組)

<!-- /TOC -->

## 我要提交資料資訊

**該倉庫為資料主倉，所有資料均由腳本自動提交匯入，請不要在該倉庫中直接提交數據資訊。若要提交數據資訊，請參考 [README](./README.md)**。

> 本平台使用石墨文檔收集數據資訊，並由腳本定時以 PR 形式提交資料到該倉庫，請不要在該倉庫中直接修改資料檔案。

> 由於參與人員較多，不開放所有人員的編輯權限，請在[這裡](https://shimo.im/forms/YVJkGrGCWwQPTpqY/fill)填寫申請，會定向邀請到特定表單中進行資訊登錄。


## 我要提 ISSUE，提 PR
這篇指南會盡可能清楚地描述 GitHub 操作流程，歡迎提交 issue， 或者直接修改提交 PR，為 **wuhan2020** 貢獻一份自己的力量！

### 0、提交 issue

有任何想法或問題，歡迎到 [此處](https://github.com/wuhan2020/wuhan2020/issues) 提交 `issue`，參與項目的志願者將會及時溝通交流。

在提交 `issue` 時，請確定 `issue` 的類型，並在標題中註明，項目的機器人將會自動打上對應的標籤：

-   hospital: 醫院相關資訊
-   factory: 生產相關資訊
-   logistical: 物流相關資訊
-   hotel: 酒店相關資訊
-   donation：捐款相關資訊
-   clinic：義診相關資訊
-   news：疫情新聞動態相關資訊
-   doc: 文件相關
-   bug： 錯誤回饋
-   feature: 新的特性

### 1、認領任務

> **衷心地希望大家能為本專案添磚加瓦，齊心協力，共體時艱！**

在 [Issue 列表](https://github.com/wuhan2020/wuhan2020/issues) 中挑選任務。然後在該 `issue` 中使用 `/self-assign`命令領取任務。項目的機器人將會自動將該`issue`的`Assignees`指定為自己。

```
/self-assign
```

示意圖如下：

![self-assign 示意圖](./static/self-assign.png)

### 2、Fork 本倉庫

訪問 [wuhan2020 倉庫的主頁](https://github.com/wuhan2020/wuhan2020)，並 Fork 到自己的帳號下。

![Fork 倉庫](./static/fork-repo.png)

> 注：以下內容是在命令列終端機內操作，需要安裝 [Git](https://git-scm.com/).

### 3、Clone 倉庫

回到自己的 GitHub 首頁，並找到剛剛 Fork 過來的 _wuhan2020_ 倉庫，進入倉庫首頁，將該倉庫 `clone` 到個人電腦（本機），如：

```bash
# 將下面的 XXX 替換成你自己的使用者名稱
git clone git@github.com:XXX/wuhan2020.git
cd wuhan2020
```

### 4、新建 `branch`

> 非緊急修復，不建議在 master 分支進行開發修改。

根據該分支的用途，起一個適當的分支名稱，建立分支，如：

```bash
git checkout -b my-fix-branch master
```

### 5、修改內容，並提交

對相應檔案做出修改，修改完成後，提交：

```bash
git add .
git commit -m "hotel: update HOTEL.csv, fix #1"
```

提交時，盡量：

(1) 用一句話清楚的描述這次提交做了什麼。

(2) 關聯相關 `issue`，如 `fix #1` 、`close #2`、`#3`

如果 `commit` 之後，又做了修改，可以使用 `--amend` 參數：

```bash
git add .
git commit --amend -sm "hotel: update HOTEL.csv, fix #1"
```

### 6、同步上游倉庫變更

同步上游倉庫變更(即 [wuhan2020/wuhan2020](https://github.com/wuhan2020/wuhan2020) )，因為可能有其他人先於你提交到上游倉庫，防止衝突：

```bash
$ git remote add upstream git@github.com:wuhan2020/wuhan2020.git
$ git fetch upstream
```

若上游倉庫有變更，需要先進行 `rebase`:

```bash
$ git rebase upstream/master
```

### 7、推送新分支到自己的遠端倉庫

```bash
$ git push -f origin my-fix-branch:my-fix-branch
```

### 8、提 `Pull Request`

在自己倉庫的頁面上提`pull request` 到上游倉庫。如下圖所示。

![pull-request](./static/pull-request.png)

![open-pr](./static/open-pr.png)
如果其他人 `review` 之後，需要再進行更改，就修改相關內容，然後執行以下操作，該 PR 將會自動同步該 `commit` 。

```bash
git add .
git commit --amend
git push -f origin my-fix-branch
```

### 9、如果你的代碼合併時出現衝突時，你可以：

> 注：如果未出現衝突，則無需進行以下操作

-   先同步上游倉庫變更

```bash
git fetch upstream
```

-   進行`rebase`:

```bash
git rebase upstream/master
```

-   手動解決衝突內容，之後重新提交：

```bash
git add my-fix-file
git rebase --continue
git push -f origin my-fix-branch
```

### 10、當你的代碼合併進去以後，你可以：

-   切回到 `master` 分支：

```bash
git checkout master -f
```

-   保持個人電腦（本機） `master` 分支與上游分支同步：

```bash
git pull --ff upstream master
```

-   刪除個人電腦（本機）分支（可選）:

```bash
git branch -D my-fix-branch
```

-   刪除遠端分支(可選)：

```bash
git push origin --delete my-fix-branch
```

## 專案機器人說明

本專案已介接 Github 機器人：`Menbotics`，該機器人可以：

-   **`Issue` 自動打標籤**：具體見 [0、提交 issue](#0提交-issue)
-   **任務認領**：具體見 [1、認領任務](#1認領任務)
-   **代碼自動合併**：有 PR(Pull Request) 提交上來之後，有代碼合併權限的人員使用 `/approve` 讓機器人自動合入代碼。

機器人配置見 [hypertrons.json](./.github/hypertrons.json)，如在該描述檔中可以看到具體有哪些人員有代碼合併權限。

## Slack 交流群組

此外，我們已經建立 [Slack 交流群組](https://join.slack.com/t/wuhan2020/shared_invite/enQtOTQxMTU4MzgyNTYwLWIxMTMyNWI4NWE2YTk3NGRjZGJhMjUzNmJhMjg1MDQ3OTEzNDE5NGY4MWFhMjRlYWU4MmE3ZGQyOGU4N2YwMzY)，已建立前端、後端、資料同步等對應 channel，歡迎大家加入共同探討各類技術或非技術類問題，讓我們大家一起齊心協力，眾志成城，共體時艱！
