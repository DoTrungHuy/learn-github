# 03 分支与 Pull Request

真实项目里，一般不建议直接在 `main` 分支上改所有内容。更常见的做法是：新建分支，在分支上修改，最后通过 Pull Request 合并。

## 1. 分支是什么

分支可以理解成项目的一条独立开发线。

```text
main
 └── feature/readme
```

`main` 分支通常保持稳定，新的功能、文档修改、实验性内容可以放在新分支里。

## 2. 为什么要用分支

使用分支的好处：

- 不会直接影响主分支；
- 可以同时做多个任务；
- 方便回退和比较；
- 方便通过 Pull Request 进行检查。

## 3. 查看当前分支

```bash
git branch
```

示例：

```text
* main
```

前面有 `*` 的就是当前分支。

## 4. 新建并切换分支

```bash
git switch -c feature/add-note
```

或者：

```bash
git checkout -b feature/add-note
```

建议分支名带上用途：

| 分支名 | 含义 |
| --- | --- |
| `feature/add-note` | 新增学习笔记 |
| `fix/readme-typo` | 修复 README 错别字 |
| `docs/git-basic` | 修改 Git 基础文档 |
| `practice/week-01` | 第一周练习 |

## 5. 在分支上提交修改

```bash
git status
git add .
git commit -m "docs: add branch note"
```

提交完成后，推送分支：

```bash
git push -u origin feature/add-note
```

## 6. 什么是 Pull Request

Pull Request 简称 PR。它的意思是：我在一个分支上完成了修改，请求把这些修改合并到另一个分支。

常见流程：

```text
新建分支 -> 修改文件 -> 提交 -> 推送分支 -> 创建 PR -> 检查 -> 合并
```

## 7. PR 里应该写什么

一个好的 PR 说明通常包括：

```markdown
## 本次修改

- 新增 Git 基础学习笔记
- 补充常用命令示例

## 为什么修改

- 方便新手按照步骤练习

## 检查情况

- [x] 本地能正常查看 Markdown
- [x] 链接路径正确
```

## 8. 合并 PR 后要做什么

PR 合并后，本地需要回到主分支并同步：

```bash
git switch main
git pull origin main
```

如果不再需要旧分支，可以删除：

```bash
git branch -d feature/add-note
```

删除远程分支：

```bash
git push origin --delete feature/add-note
```

## 9. main 分支和 feature 分支的区别

| 分支 | 作用 |
| --- | --- |
| `main` | 稳定版本，尽量保持可用 |
| `feature/*` | 新功能或新内容 |
| `fix/*` | 修复问题 |
| `docs/*` | 文档修改 |

## 10. 本节练习

1. 创建一个新分支：

```bash
git switch -c practice/branch-demo
```

2. 新建一个文件：

```text
branch-demo.md
```

3. 在文件里写下：

```markdown
# Branch Demo

这是我第一次练习 Git 分支。
```

4. 提交修改：

```bash
git add .
git commit -m "docs: add branch demo"
```

5. 推送分支：

```bash
git push -u origin practice/branch-demo
```

6. 到 GitHub 网页上创建 Pull Request；
7. 检查无误后合并；
8. 回到本地同步 main：

```bash
git switch main
git pull origin main
```
