# 02 GitHub 远程仓库流程

这一节主要解决一个问题：本地写好的内容，怎样同步到 GitHub 上。

## 1. 远程仓库是什么

远程仓库就是放在 GitHub 服务器上的仓库。

本地仓库和远程仓库的关系可以理解为：

```text
你的电脑里的项目  <->  GitHub 上的项目
```

本地提交不会自动出现在 GitHub 上，必须通过 `git push` 推送。

## 2. 查看是否关联远程仓库

```bash
git remote -v
```

如果已经关联，会看到类似：

```text
origin  https://github.com/DoTrungHuy/learn-github.git (fetch)
origin  https://github.com/DoTrungHuy/learn-github.git (push)
```

其中 `origin` 是远程仓库的默认名字。

## 3. 添加远程仓库

如果本地仓库还没有关联 GitHub，可以执行：

```bash
git remote add origin https://github.com/用户名/仓库名.git
```

例如：

```bash
git remote add origin https://github.com/DoTrungHuy/learn-github.git
```

添加后再检查：

```bash
git remote -v
```

## 4. 第一次推送

```bash
git push -u origin main
```

这里的含义是：

| 部分 | 含义 |
| --- | --- |
| `git push` | 推送本地提交 |
| `origin` | 推送到名为 origin 的远程仓库 |
| `main` | 推送 main 分支 |
| `-u` | 建立本地分支和远程分支的默认关联 |

第一次使用 `-u` 后，以后通常只需要：

```bash
git push
```

## 5. 从 GitHub 拉取最新内容

```bash
git pull origin main
```

`pull` 可以理解为：把 GitHub 上别人或网页端的新修改同步到本地。

如果你在 GitHub 网页上修改了 README，本地电脑还没有这些修改，那么本地继续 `push` 时可能会失败。此时通常需要先：

```bash
git pull origin main
```

再：

```bash
git push origin main
```

## 6. 标准远程同步流程

日常推荐流程：

```bash
git pull origin main
git status
git add .
git commit -m "docs: update notes"
git push origin main
```

如果确定远程没有变化，也可以省略第一步，但新手阶段建议先 `pull`。

## 7. 克隆仓库

如果项目已经在 GitHub 上，可以用 `clone` 下载到本地：

```bash
git clone https://github.com/DoTrungHuy/learn-github.git
```

克隆后会得到一个同名文件夹：

```text
learn-github/
```

进入项目：

```bash
cd learn-github
```

## 8. 本地和远程不同步怎么办

最常见情况：

```text
Updates were rejected because the remote contains work that you do not have locally.
```

意思是：远程仓库有本地没有的提交。解决思路：

```bash
git pull origin main
git push origin main
```

如果 `pull` 时出现冲突，就要先解决冲突，再提交。

## 9. 本节练习

1. 在 GitHub 网页上修改一次 README；
2. 回到本地执行 `git pull origin main`；
3. 本地新增一行内容；
4. 执行 `git add .`；
5. 执行 `git commit -m "docs: practice remote workflow"`；
6. 执行 `git push origin main`；
7. 回到 GitHub 网页检查是否更新成功。
