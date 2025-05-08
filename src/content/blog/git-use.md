---
title: "如何用Git高效管理代码版本"
description: "如何用Git高效管理代码版本"
pubDate: "Jun 01 2024"
heroImage: "/blog-placeholder-5.jpg"
---

# 引言

Git 是前端开发中最重要的工具之一，但许多新手对其分支管理、提交规范感到困惑。

## 核心内容

### 基础命令

```bash
git init        # 初始化仓库
git add .       # 添加所有文件到暂存区
git commit -m "描述"  # 提交代码
git status      # 查看当前状态
```

### 分支管理

- 主分支：main（或 master）用于生产环境代码。
- 开发分支：dev 用于日常开发。
- 功能分支：feature/xxx 用于开发新功能（如 feature/login）。

### 提交规范

使用统一的提交信息格式：type(scope): description
示例：

```bash
feat(auth): add login form
fix(button): resolve click event bug
```

### 协作流程

- 拉取代码：git pull origin main
- 推送代码：git push origin dev
- 合并分支：
  ```bash
  git checkout main
  git merge dev
  ```

### 常见问题

- Q：如何撤销错误的提交？
  - A：使用 git reset --soft HEAD~1（撤销最后一次提交，保留代码）。
