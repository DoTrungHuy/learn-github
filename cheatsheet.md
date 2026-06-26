# Git 命令速查表

这份速查表适合在日常练习时打开对照。刚开始不用全部背下来，先把最常用的一组命令用熟。

## 1. 查看当前状态

```bash
git status
```

作用：查看哪些文件被修改、新增、删除，以及是否已经加入暂存区。

学习 Git 时，遇到不确定情况先执行 `git status`，它通常会告诉你下一步应该做什么。

## 2. 添加文件到暂存区

添加全部修改：

```bash
git add .
```

添加指定文件：

```bash
git add README.md
```

暂存区可以理解为“准备提交的修改清单”。

## 3. 提交修改

```bash
git commit -m "docs: update README"
```

提交信息建议写清楚这次做了什么，不要只写 `update`、`test`、`1`。

## 4. 查看提交历史

简洁查看：

```bash
git log --oneline
```

完整查看：

```bash
git log
```

退出 `git log` 页面时按：

```text
q
```

## 5. 查看分支

```bash
git branch
```

查看本地和远程分支：

```bash
git branch -a
```

当前所在分支前面会有 `*`。

## 6. 创建并切换分支

```bash
git checkout -b feature/readme
```

或者使用新版写法：

```bash
git switch -c feature/readme
```

分支名建议能看出用途，例如：

```text
feature/add-note
fix/typo
practice/week-01
```

## 7. 切换分支

```bash
git checkout main
```

或：

```bash
git switch main
```

## 8. 合并分支

先切回目标分支：

```bash
git switch main
```

再合并：

```bash
git merge feature/readme
```

## 9. 查看远程仓库

```bash
git remote -v
```

如果能看到 GitHub 地址，说明本地仓库已经关联远程仓库。

## 10. 添加远程仓库

```bash
git remote add origin https://github.com/用户名/仓库名.git
```

如果已经存在 `origin`，不要重复添加，可以先查看：

```bash
git remote -v
```

## 11. 推送到 GitHub

第一次推送并绑定上游分支：

```bash
git push -u origin main
```

之后一般可以直接：

```bash
git push
```

## 12. 从 GitHub 拉取最新内容

```bash
git pull origin main
```

如果提示远程有新提交，本地没有，需要先 `pull` 再 `push`。

## 13. 克隆仓库

```bash
git clone https://github.com/用户名/仓库名.git
```

克隆后会自动生成一个项目文件夹。

## 14. 撤销还没暂存的修改

撤销单个文件：

```bash
git checkout -- README.md
```

新版写法：

```bash
git restore README.md
```

注意：这个操作会丢弃本地修改，执行前要确认真的不要了。

## 15. 取消暂存

```bash
git restore --staged README.md
```

这个命令只是把文件从暂存区拿出来，不会删除文件内容。

## 16. 常用组合流程

最常见的一次提交流程：

```bash
git status
git add .
git commit -m "docs: add notes"
git push
```

推送前先同步远程：

```bash
git pull origin main
git push origin main
```

新建分支开发：

```bash
git switch -c feature/new-note
git add .
git commit -m "docs: add new note"
git push -u origin feature/new-note
```
