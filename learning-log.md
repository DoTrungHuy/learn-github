# GitHub 学习记录

这个文件用来记录每次学习 Git/GitHub 时做了什么、遇到了什么问题、最后怎么解决。以后如果再次遇到类似问题，可以直接回来查。

## 记录模板

````markdown
## 日期：2026-xx-xx

### 今天学习了什么

- 

### 今天练习了什么命令

```bash

```

### 遇到的问题

- 问题现象：
- 报错信息：
- 原因分析：
- 解决方法：

### 今天的收获

- 
````

---

## 示例记录

## 日期：2026-06-26

### 今天学习了什么

- 学会了查看仓库状态；
- 学会了把文件加入暂存区；
- 学会了提交一次修改；
- 理解了 `git add` 和 `git commit` 的区别。

### 今天练习了什么命令

```bash
git status
git add README.md
git commit -m "docs: update README"
git log --oneline
```

### 遇到的问题

- 问题现象：执行 `git push` 时失败；
- 报错信息：`Updates were rejected because the remote contains work that you do not have locally.`；
- 原因分析：远程仓库有新的提交，本地没有同步；
- 解决方法：先执行 `git pull origin main`，再重新 `git push`。

### 今天的收获

- 不要一报错就乱敲命令，先看报错信息；
- `git status` 是排查问题的第一步；
- 推送失败不一定是坏事，很多时候只是本地和远程不同步。

---

## 我的学习记录

从这里开始继续往下写。
