# 🚀 learn-github

![GitHub repo size](https://img.shields.io/github/repo-size/DoTrungHuy/learn-github?style=flat-square&logo=github)
![GitHub last commit](https://img.shields.io/github/last-commit/DoTrungHuy/learn-github?style=flat-square&logo=github)
![Made with Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f?style=flat-square&logo=markdown)
![Learning Git](https://img.shields.io/badge/Learning-Git-F05032?style=flat-square&logo=git&logoColor=white)
![GitHub](https://img.shields.io/badge/Platform-GitHub-181717?style=flat-square&logo=github)

一个从零开始学习 **Git 与 GitHub** 的练习仓库。这个项目不是单纯放笔记，而是把 GitHub 常见操作拆成可以一步一步完成的小任务，适合第一次系统学习 GitHub 的同学。

---

## 🎯 项目目标

通过这个仓库，你可以学会：

- 🧠 Git 的基本概念：仓库、提交、分支、远程仓库；
- 🛠️ GitHub 的基本操作：创建仓库、提交代码、查看历史、管理文件；
- 🌿 常用协作流程：branch、Pull Request、merge、issue；
- 🧯 常见报错处理：push 被拒绝、冲突、分支不一致、代理问题；
- 📝 规范项目记录习惯：README、学习日志、提交信息。

## 👥 适合人群

- 🎓 刚开始接触 GitHub 的计算机学生；
- 💻 想把课堂作业、实验报告、个人项目放到 GitHub 上的人；
- 🌟 想为后续开源项目、比赛项目、就业简历积累项目经验的人。

## 🗂️ 仓库结构

```text
learn-github/
├── README.md                 # 项目首页说明
├── cheatsheet.md             # 常用命令速查表
├── learning-log.md           # 学习记录模板
├── docs/
│   ├── 01-git-basic.md        # Git 基础概念与本地操作
│   ├── 02-github-workflow.md  # GitHub 远程仓库流程
│   ├── 03-branch-pr.md        # 分支与 Pull Request
│   └── 04-common-errors.md    # 常见错误与解决方法
└── exercises/
    └── week-01.md             # 第一周练习任务
```

## 🧭 学习路线

| 阶段 | 内容 | 入口 |
| --- | --- | --- |
| ① | 🧠 理解 Git 和 GitHub 的区别 | [Git 基础概念与本地操作](docs/01-git-basic.md) |
| ② | ✅ 完成第一次 add / commit | [Git 命令速查表](cheatsheet.md) |
| ③ | ☁️ 把本地仓库推送到 GitHub | [GitHub 远程仓库流程](docs/02-github-workflow.md) |
| ④ | 🌿 学习分支和 Pull Request | [分支与 Pull Request](docs/03-branch-pr.md) |
| ⑤ | 🧯 处理常见报错 | [常见错误与解决方法](docs/04-common-errors.md) |
| ⑥ | 📓 记录自己的学习过程 | [GitHub 学习记录](learning-log.md) |
| ⑦ | 🏁 完成第一周任务 | [Week 01 GitHub 入门练习](exercises/week-01.md) |

## ⚡ 快速开始

### 1. 克隆仓库

```bash
git clone https://github.com/DoTrungHuy/learn-github.git
cd learn-github
```

### 2. 查看当前状态

```bash
git status
```

### 3. 修改文件后提交

```bash
git add .
git commit -m "docs: update learning note"
```

### 4. 推送到 GitHub

```bash
git push origin main
```

## 🧩 Git 与 GitHub 的关系

```text
Git：本地版本控制工具
GitHub：远程代码托管平台

本地修改 -> git add -> git commit -> git push -> GitHub 仓库更新
```

## 🧪 推荐练习顺序

1. 📖 阅读 `docs/01-git-basic.md`；
2. ⌨️ 对照 `cheatsheet.md` 敲一遍基础命令；
3. 📝 在 `learning-log.md` 记录一次学习过程；
4. 🌿 新建一个分支并推送；
5. 🔀 在 GitHub 网页上创建 Pull Request；
6. 🧯 遇到报错后整理到 `docs/04-common-errors.md` 或自己的学习日志中。

## 🧱 提交信息规范

建议采用简单的提交格式：

```text
类型: 做了什么事情
```

常见类型：

| 类型 | 含义 | 示例 |
| --- | --- | --- |
| `docs` | 📚 文档修改 | `docs: update README` |
| `feat` | ✨ 新功能 | `feat: add practice file` |
| `fix` | 🐛 修复问题 | `fix: correct typo` |
| `chore` | 🔧 杂项维护 | `chore: update .gitignore` |
| `refactor` | ♻️ 重构 | `refactor: reorganize notes` |

## 💡 学习建议

不要只看命令，要真的敲一遍。GitHub 学习最重要的不是背命令，而是知道：

1. 📍 我现在在哪个分支？
2. 📄 哪些文件被修改了？
3. ✅ 这些修改有没有提交？
4. ☁️ 本地和远程是否同步？
5. 🧯 报错信息到底在提醒什么？

只要能围绕这几个问题排查，大部分 GitHub 问题都能自己解决。

## 🔮 后续可以扩展的内容

- 🌐 增加 GitHub Pages 教程；
- 🤖 增加 GitHub Actions 入门；
- 🌍 增加开源项目贡献流程；
- ✍️ 增加 Markdown 写作规范；
- 🧑‍💼 增加适合学生简历展示的项目模板。
