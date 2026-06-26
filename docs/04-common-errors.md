# 04 常见错误与解决方法

Git/GitHub 新手最怕的不是命令不会，而是看到一大段英文报错就慌。其实很多报错都有固定原因和固定处理思路。

建议遇到问题时先做三件事：

```bash
git status
git branch
git remote -v
```

这三个命令能帮你确认：当前文件状态、当前分支、远程仓库地址。

## 1. push 被拒绝

### 报错示例

```text
Updates were rejected because the remote contains work that you do not have locally.
```

### 原因

远程仓库有新的提交，而你的本地仓库还没有这些提交。

常见场景：

- 你在 GitHub 网页上改了 README；
- 另一台电脑推送过代码；
- 其他人合并了新的 PR。

### 解决方法

```bash
git pull origin main
git push origin main
```

如果 `pull` 出现冲突，先解决冲突，再提交。

## 2. 当前分支不是 main

### 现象

你以为自己在 `main`，但实际在别的分支上。

### 检查方法

```bash
git branch
```

看到 `*` 在哪个分支前面，说明当前就在那个分支。

### 解决方法

切回 main：

```bash
git switch main
```

或：

```bash
git checkout main
```

## 3. 没有提交就 push

### 现象

执行 `git push` 后，GitHub 页面没有变化。

### 原因

你可能只是修改了文件，但没有 `add` 和 `commit`。

### 检查方法

```bash
git status
```

如果看到有 modified 或 untracked 文件，说明还没提交。

### 解决方法

```bash
git add .
git commit -m "docs: update files"
git push
```

## 4. remote origin already exists

### 报错示例

```text
fatal: remote origin already exists.
```

### 原因

你已经添加过名为 `origin` 的远程仓库，又重复添加了一次。

### 解决方法

先查看：

```bash
git remote -v
```

如果地址正确，就不需要再添加。

如果地址不正确，可以修改：

```bash
git remote set-url origin https://github.com/用户名/仓库名.git
```

## 5. authentication failed

### 现象

推送时提示认证失败。

### 常见原因

- GitHub 不再支持直接用账号密码推送；
- token 过期；
- 凭据缓存里保存了错误账号；
- 当前 GitHub 账号没有仓库权限。

### 处理思路

1. 确认仓库是不是自己的；
2. 确认远程地址是否正确：

```bash
git remote -v
```

3. 如果用 HTTPS，检查 token；
4. 如果经常使用 GitHub，可以考虑配置 SSH Key。

## 6. merge conflict 合并冲突

### 报错示例

```text
CONFLICT (content): Merge conflict in README.md
```

### 原因

本地和远程都修改了同一个文件的同一部分，Git 不知道应该保留哪一个。

### 冲突文件示例

```text
<<<<<<< HEAD
这是我本地的内容
=======
这是远程仓库的内容
>>>>>>> origin/main
```

### 解决方法

手动编辑文件，保留正确内容，删除这些标记：

```text
<<<<<<<
=======
>>>>>>>
```

然后执行：

```bash
git add .
git commit -m "fix: resolve merge conflict"
git push
```

## 7. 文件太大无法上传

### 报错示例

```text
File is larger than 100 MB
```

### 原因

GitHub 普通仓库不适合直接放很大的文件，比如数据集、压缩包、视频、大模型权重。

### 解决思路

- 删除大文件；
- 使用 `.gitignore` 忽略；
- 必要时使用 Git LFS；
- 大型数据集放网盘或专门的数据平台。

## 8. 不小心提交了不该提交的文件

比如：

- `.env`；
- token；
- 密码；
- 大文件；
- 临时文件。

如果只是普通文件，可以删除后重新提交：

```bash
git rm 文件名
git commit -m "chore: remove unnecessary file"
git push
```

如果提交了密码、token 这类敏感信息，不要只删除文件，应该立刻作废旧 token 或修改密码。

## 9. 代理导致 GitHub 连接失败

### 现象

可能出现：

```text
Failed to connect to github.com
```

或者长时间卡住。

### 检查代理配置

```bash
git config --global --get http.proxy
git config --global --get https.proxy
```

### 设置代理示例

```bash
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890
```

### 取消代理

```bash
git config --global --unset http.proxy
git config --global --unset https.proxy
```

## 10. 排查问题的固定顺序

遇到任何 Git 问题，先按这个顺序检查：

```bash
git status
git branch
git remote -v
git log --oneline -5
```

然后问自己：

1. 我现在在哪个分支？
2. 文件有没有保存？
3. 修改有没有 `git add`？
4. 修改有没有 `git commit`？
5. 本地有没有先 `git pull`？
6. 远程地址是不是我要推送的仓库？

很多问题都能在这六个问题里找到原因。
