# learn-github

一个从零开始学习 **Git 与 GitHub** 的练习仓库。这个项目不是单纯放笔记，而是把 GitHub 常见操作拆成可以一步一步完成的小任务，适合第一次系统学习 GitHub 的同学。

## 项目目标

通过这个仓库，你可以学会：

- Git 的基本概念：仓库、提交、分支、远程仓库；
- GitHub 的基本操作：创建仓库、提交代码、查看历史、管理文件；
- 常用协作流程：branch、Pull Request、merge、issue；
- 常见报错处理：push 被拒绝、冲突、分支不一致、代理问题；
- 养成规范的项目记录习惯：README、学习日志、提交信息。

## 适合人群

- 刚开始接触 GitHub 的计算机学生；
- 想把课堂作业、实验报告、个人项目放到 GitHub 上的人；
- 想为后续开源项目、比赛项目、就业简历积累项目经验的人。

## 仓库结构

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

## 推荐学习路线

### 第 1 步：理解 Git 和 GitHub 的区别

Git 是本地版本控制工具，负责记录文件变化；GitHub 是代码托管平台，负责把仓库放到网上，方便备份、展示和协作。

先看：[Git 基础概念与本地操作](docs/01-git-basic.md)

### 第 2 步：完成第一次提交

重点掌握下面这组命令：

```bash
git status
git add .
git commit -m "docs: add learning note"
git log --oneline
```

### 第 3 步：把本地仓库推送到 GitHub

重点掌握：

```bash
git remote -v
git push origin main
git pull origin main
```

先看：[GitHub 远程仓库流程](docs/02-github-workflow.md)

### 第 4 步：学习分支与 PR

真实项目里一般不会直接在 `main` 分支上改，而是新建分支，修改后通过 Pull Request 合并。

先看：[分支与 Pull Request](docs/03-branch-pr.md)

### 第 5 步：整理自己的学习记录

每次练习后，把遇到的问题写到 [learning-log.md](learning-log.md)，以后遇到相同报错就不用重新查。

## 常用命令入口

- [Git 命令速查表](cheatsheet.md)
- [常见错误与解决方法](docs/04-common-errors.md)
- [第一周练习任务](exercises/week-01.md)

## 提交信息规范

建议采用简单的提交格式：

```text
类型: 做了什么事情
```

常见类型：

| 类型 | 含义 | 示例 |
| --- | --- | --- |
| docs | 文档修改 | `docs: update README` |
| feat | 新功能 | `feat: add practice file` |
| fix | 修复问题 | `fix: correct typo` |
| chore | 杂项维护 | `chore: update .gitignore` |
| refactor | 重构 | `refactor: reorganize notes` |

## 学习建议

不要只看命令，要真的敲一遍。GitHub 学习最重要的不是背命令，而是知道：

1. 我现在在哪个分支？
2. 哪些文件被修改了？
3. 这些修改有没有提交？
4. 本地和远程是否同步？
5. 报错信息到底在提醒什么？

只要能围绕这几个问题排查，大部分 GitHub 问题都能自己解决。

## 后续可以扩展的内容

- 增加 GitHub Pages 教程；
- 增加 GitHub Actions 入门；
- 增加开源项目贡献流程；
- 增加 Markdown 写作规范；
- 增加适合学生简历展示的项目模板。
