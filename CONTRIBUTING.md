# 贡献指南

感谢参与本项目。开始之前请先读完本文，能省掉大部分返工。

## 环境准备

<!-- 技术栈确定后在此补充。示例：

### 需要
- Node.js 22+
- pnpm 9+

### 初始化
```bash
pnpm install
pnpm dev
```
-->

> TODO：技术栈确定后补充运行时版本与初始化命令。

另外建议 Windows 用户先执行一次，避免换行符造成整文件 diff：

```bash
git config core.autocrlf false
```

仓库已通过 `.gitattributes` 统一为 LF。

## 分支模型

采用 GitHub Flow：`main` 始终可运行，所有改动经由短分支 + Pull Request 合并。

| 分支 | 用途 |
| --- | --- |
| `main` | 稳定分支，受保护，禁止直接推送 |
| `feat/<简短描述>` | 新功能 |
| `fix/<简短描述>` | 缺陷修复 |
| `docs/<简短描述>` | 仅文档变更 |
| `chore/<简短描述>` | 构建、依赖、配置等杂项 |

命名用英文小写短横线，例如 `feat/user-login`、`fix/export-encoding`。

**分支存活时间控制在 1–3 天。** 做不完就先开 Draft PR，让别人能看到方向，避免长期分支最后合并时冲突爆炸。

## 提交信息

遵循 Conventional Commits：

```
<类型>(<范围>): <简短说明>
```

| 类型 | 含义 |
| --- | --- |
| `feat` | 新功能 |
| `fix` | 缺陷修复 |
| `docs` | 文档 |
| `refactor` | 重构（不改变外部行为） |
| `perf` | 性能优化 |
| `test` | 测试 |
| `build` | 构建系统或依赖 |
| `ci` | CI 配置 |
| `chore` | 其他杂项 |

示例：

```
feat(auth): 支持记住登录状态
fix(export): 修复 UTF-8 环境下中文文件名乱码
```

说明部分用中文即可，一行不超过 72 字符，不要以句号结尾。

## 提交流程

```bash
# 1. 同步主干并开分支
git switch main
git pull
git switch -c feat/your-feature

# 2. 开发，小步提交
git add -A
git commit -m "feat: 实现 xxx"

# 3. 推送并开 PR
git push -u origin feat/your-feature
gh pr create --fill
```

## Pull Request 要求

- **单个 PR 控制在 400 行以内**。改动过大请拆成多个 PR，或先开 Issue 讨论方案。
- 标题同样使用 Conventional Commits 格式。
- 描述里必须写清楚：改了什么、为什么改、怎么验证。
- 自己先跑通构建与测试，再请求评审。
- 合并方式统一使用 **Squash merge**，一个 PR 对应 main 上一条提交。
- 合并后由作者删除远端分支。

## 评审

- 收到评审意见后，在同一分支追加提交，不要重建 PR。
- 所有对话标记为已解决后才能合并。
- 评审者的意见请回复"已修改"或说明为何不采纳，不要静默忽略。

## 代码风格

<!-- 技术栈确定后补充：格式化工具、lint 规则、命名约定。 -->

> TODO：确定技术栈后补充格式化与 lint 命令，并在 CI 中强制检查。

## 报告问题

请使用仓库的 Issue 模板。提缺陷时附上复现步骤、期望行为、实际行为和环境信息。

**不要**在 Issue 或 PR 中粘贴密钥、Token、真实用户数据。
