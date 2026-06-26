# 贡献指南

这个仓库是一个 GitHub 学习练习项目，欢迎用它来练习 issue、branch、commit、Pull Request 等操作。

## 1. 推荐贡献内容

你可以贡献：

- 修正错别字；
- 补充 Git 命令解释；
- 增加常见报错案例；
- 新增练习任务；
- 改进 README 排版；
- 添加 Markdown 写作示例。

## 2. 不建议提交的内容

请不要提交：

- 账号密码、token、密钥；
- 大型压缩包、视频、数据集；
- 与 Git/GitHub 学习完全无关的内容；
- 临时文件，例如 `.tmp`、`.bak`、系统缓存文件。

## 3. 推荐分支命名

| 类型 | 示例 | 含义 |
| --- | --- | --- |
| 文档 | `docs/update-readme` | 修改文档 |
| 修复 | `fix/typo` | 修复错别字或错误 |
| 练习 | `practice/week-01` | 学习练习分支 |
| 功能 | `feat/add-github-pages-guide` | 新增内容 |

## 4. 推荐提交信息

格式：

```text
类型: 简短说明
```

示例：

```bash
git commit -m "docs: add Git branch note"
git commit -m "fix: correct README typo"
git commit -m "chore: add gitignore"
```

## 5. Pull Request 流程

### 第一步：创建分支

```bash
git switch -c docs/update-note
```

### 第二步：修改文件

例如修改 README 或 docs 里的学习笔记。

### 第三步：提交修改

```bash
git add .
git commit -m "docs: update learning note"
```

### 第四步：推送分支

```bash
git push -u origin docs/update-note
```

### 第五步：创建 Pull Request

到 GitHub 网页上点击 `Compare & pull request`，填写说明后提交。

## 6. PR 检查清单

提交 PR 前请检查：

- [ ] 文件路径正确；
- [ ] Markdown 可以正常显示；
- [ ] 链接没有写错；
- [ ] 没有提交密码、token、大文件；
- [ ] 提交信息能看出本次修改内容。

## 7. 学习重点

这个仓库的重点不是“一次就做对”，而是通过不断练习理解 GitHub 的工作流程。

遇到报错时，不要急着复制命令。先看：

```bash
git status
git branch
git remote -v
```

再判断问题出在文件状态、分支，还是远程仓库同步上。
