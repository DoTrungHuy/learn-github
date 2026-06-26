# 01 Git 基础概念与本地操作

Git 是一个版本控制工具。它最核心的作用是：记录文件每一次重要修改，并且允许你回看、比较、恢复这些修改。

## 1. 为什么需要 Git

如果没有 Git，很多人管理文件会变成这样：

```text
实验报告.docx
实验报告-修改版.docx
实验报告-最终版.docx
实验报告-最终版2.docx
实验报告-真的最终版.docx
```

这种方式的问题是：

- 不知道每个版本到底改了什么；
- 文件多了之后很乱；
- 出错后很难回退；
- 多人协作时容易互相覆盖。

Git 的做法是：保留一个项目文件夹，然后用提交记录保存每个版本。

## 2. Git 和 GitHub 的区别

| 名称 | 作用 | 可以简单理解成 |
| --- | --- | --- |
| Git | 本地版本控制工具 | 记录修改历史的软件 |
| GitHub | 远程代码托管平台 | 放在网上的项目仓库 |

一句话：Git 负责版本控制，GitHub 负责在线托管和协作。

## 3. 仓库 Repository

仓库就是一个被 Git 管理的项目文件夹。

如果一个文件夹里有 `.git` 隐藏目录，说明它已经是 Git 仓库。

初始化仓库：

```bash
git init
```

查看当前目录下是否有 `.git`：

```bash
ls -a
```

Windows PowerShell 可以用：

```powershell
dir -Force
```

## 4. 工作区、暂存区、版本库

Git 的一次提交大致分为三个区域：

```text
工作区 -> 暂存区 -> 版本库
```

| 区域 | 含义 | 对应命令 |
| --- | --- | --- |
| 工作区 | 你正在编辑的文件 | 直接修改文件 |
| 暂存区 | 准备提交的修改 | `git add` |
| 版本库 | 已经保存的历史版本 | `git commit` |

常见流程：

```bash
git status
git add .
git commit -m "docs: add notes"
```

## 5. 第一次本地提交

### 第一步：查看状态

```bash
git status
```

如果看到红色文件，通常表示文件被修改了，但还没有加入暂存区。

### 第二步：加入暂存区

```bash
git add .
```

`.` 表示当前目录下的所有修改。

### 第三步：提交

```bash
git commit -m "docs: first commit"
```

`-m` 后面写的是提交说明。

## 6. 查看提交历史

```bash
git log --oneline
```

示例：

```text
a1b2c3d docs: first commit
```

前面的 `a1b2c3d` 是提交编号的一部分，后面是提交说明。

## 7. 修改文件后的标准流程

每次改完文件，可以按这个顺序来：

```bash
git status
git add .
git commit -m "docs: update note"
git log --oneline
```

## 8. 新手最容易混淆的地方

### `git add` 不是上传

`git add` 只是把修改放到暂存区，还没有保存成版本，也没有传到 GitHub。

### `git commit` 也不是上传

`git commit` 是保存到本地版本库，还没有传到 GitHub。

### `git push` 才是上传到远程仓库

本地提交之后，还要执行：

```bash
git push
```

才会同步到 GitHub。

## 9. 本节练习

1. 新建一个 `notes.md` 文件；
2. 写入一段今天学到的 Git 知识；
3. 执行 `git status`；
4. 执行 `git add notes.md`；
5. 执行 `git commit -m "docs: add git notes"`；
6. 执行 `git log --oneline` 查看历史。

完成后，把过程写到 `learning-log.md`。
