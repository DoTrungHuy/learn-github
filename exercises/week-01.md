# Week 01 GitHub 入门练习

这一周的目标不是学很多命令，而是把最核心的 GitHub 流程跑通：修改文件、提交、推送、查看历史。

## 练习前准备

确认已经安装 Git：

```bash
git --version
```

确认当前在项目目录：

```bash
pwd
```

Windows PowerShell 可以用：

```powershell
Get-Location
```

查看当前仓库状态：

```bash
git status
```

## 任务 1：修改 README

### 要求

在 `README.md` 中新增一小段自己的学习目标，例如：

```markdown
## 我的学习目标

- 学会 Git 的基本命令；
- 学会把项目推送到 GitHub；
- 学会使用分支和 Pull Request。
```

### 操作步骤

```bash
git status
git add README.md
git commit -m "docs: add learning goals"
git push origin main
```

### 检查点

- GitHub 网页上的 README 是否更新；
- `git log --oneline` 是否能看到刚才的提交。

## 任务 2：新增学习笔记

### 要求

新建文件：

```text
notes/git-basic-note.md
```

写入内容：

```markdown
# Git 基础笔记

## 我今天理解的 Git

Git 是一个版本控制工具，可以记录项目文件的变化。

## 我最常用的三个命令

- git status
- git add .
- git commit -m "说明"
```

如果没有 `notes` 文件夹，可以先创建。

### 操作步骤

```bash
git status
git add notes/git-basic-note.md
git commit -m "docs: add git basic note"
git push origin main
```

## 任务 3：练习分支

### 要求

新建一个分支，在分支上新增文件，再推送到 GitHub。

### 操作步骤

```bash
git switch -c practice/week-01
```

新建文件：

```text
practice-week-01.md
```

写入：

```markdown
# Week 01 Practice

这是我第一次使用 Git 分支完成练习。
```

提交并推送：

```bash
git add .
git commit -m "docs: add week 01 practice"
git push -u origin practice/week-01
```

然后去 GitHub 网页创建 Pull Request。

## 任务 4：记录一次错误

故意不要害怕报错。学习 GitHub 时，能看懂报错比一次成功更重要。

在 `learning-log.md` 里记录一次你遇到的问题，格式如下：

```markdown
## 日期：2026-xx-xx

### 遇到的问题

- 问题现象：
- 报错信息：
- 原因分析：
- 解决方法：
```

## 完成标准

完成本周练习后，你应该能够：

- [ ] 看懂 `git status` 的基本输出；
- [ ] 完成一次 `add -> commit -> push`；
- [ ] 查看提交历史；
- [ ] 新建分支并推送；
- [ ] 在 GitHub 上创建 Pull Request；
- [ ] 把一次报错记录到学习日志中。

## 常见问题提醒

### 为什么 GitHub 上没有变化？

检查是否忘了：

```bash
git add .
git commit -m "说明"
git push
```

### 为什么 push 失败？

先试试：

```bash
git pull origin main
git push origin main
```

### 怎么知道我在哪个分支？

```bash
git branch
```

有 `*` 的就是当前分支。
