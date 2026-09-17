---
title: Claude Code Skills 完整总结
---

# Claude Code Skills 完整总结

> 最后更新: 2026年6月18日
> Claude Code 版本: 2.1.181
> 用户安装 Skills 路径: `~/.claude/skills/`

---

## 📋 目录

- [第一部分：Claude Code 内置命令](#第一部分claude-code-内置命令)
- [第二部分：用户安装的 Skills](#第二部分用户安装的-skills)
  - [Superpowers 开发工作流系列](#superpowers-开发工作流系列)
  - [Nature 学术写作系列](#nature-学术写作系列)
  - [开发工具类 Skills](#开发工具类-skills)

---

# 第一部分：Claude Code 内置命令

这些是 Claude Code CLI 自带的核心斜杠命令，无需额外安装。

## 核心会话命令

| 命令 | 功能说明 | 使用示例 |
|------|----------|----------|
| `/help` | 显示帮助信息和可用命令列表 | `/help` |
| `/clear` | 清除当前对话上下文 | `/clear` |
| `/compact` | 压缩对话历史以减少 token 占用 | `/compact` |
| `/continue` | 继续当前目录最近的对话 | `/continue` 或 `claude -c` |
| `/resume` | 恢复之前的会话 | `/resume` |
| `/rename` | 重命名当前会话 | `/rename <name>` |
| `/copy` | 复制上一条回复到剪贴板 | `/copy` |

## 配置与设置命令

| 命令 | 功能说明 | 使用示例 |
|------|----------|----------|
| `/config` | 查看或修改配置设置 | `/config thinking=false` |
| `/model` | 切换当前会话使用的模型 | `/model` |
| `/effort` | 调整推理努力程度 (low/medium/high/xhigh/max) | `/effort high` |
| `/permissions` | 查看/管理工具权限规则 | `/permissions` |
| `/login` | 切换 Anthropic 账户 | `/login` |
| `/logout` | 登出当前账户 | `/logout` |
| `/vim` | 切换 vim 键绑定模式 | `/vim` |

## 诊断与维护命令

| 命令 | 功能说明 | 使用示例 |
|------|----------|----------|
| `/doctor` | 检查 Claude Code 配置健康状态 | `/doctor` |
| `/cost` | 显示当前会话的 token 使用量和费用 | `/cost` |
| `/stats` | 显示会话统计信息 | `/stats` |
| `/usage` | 显示详细的使用量分解 | `/usage` |
| `/usage-credits` | 查看使用额度信息 | `/usage-credits` |

## 项目与文件命令

| 命令 | 功能说明 | 使用示例 |
|------|----------|----------|
| `/init` | 初始化项目的 CLAUDE.md 记忆文件 | `/init` |
| `/memory` | 编辑 CLAUDE.md 记忆文件 | `/memory` |
| `/cd` | 切换会话的工作目录 | `/cd <path>` |

## 扩展与集成命令

| 命令 | 功能说明 | 使用示例 |
|------|----------|----------|
| `/mcp` | 管理 Model Context Protocol 服务器 | `/mcp` |
| `/plugin` | 管理 Claude Code 插件 | `/plugin` |
| `/reload-skills` | 重新扫描 skill 目录 | `/reload-skills` |
| `/ide` | 配置 IDE 集成 | `/ide` |
| `/terminal-setup` | 配置终端集成 | `/terminal-setup` |
| `/remote-control` | 启用远程控制会话 | `/remote-control` |
| `/chrome` | 启用 Claude in Chrome 集成 | `/chrome` |

## 高级功能命令

| 命令 | 功能说明 | 使用示例 |
|------|----------|----------|
| `/bg` | 将当前会话转到后台运行 | `/bg` |
| `/workflows` | 查看和管理工作流运行 | `/workflows` |
| `/review` | 请求代码审查 | `/review` |
| `/simplify` | 运行代码简化审查并应用修复 | `/simplify` |
| `/autofix-pr` | 自动修复 PR 中的问题 | `/autofix-pr` |
| `/btw` | 快速提问而不打断当前任务 | `/btw <question>` |
| `/voice` | 切换语音输入模式 | `/voice` |
| `/goal` | 设置当前会话目标 | `/goal` |
| `/loop` | 设置循环执行的任务 | `/loop` |
| `/advisor` | 配置顾问模型 | `/advisor` |

## 快捷键参考

| 快捷键 | 功能 |
|--------|------|
| `Ctrl+C` | 中断当前操作 |
| `Ctrl+O` | 展开/查看完整输出 |
| `Ctrl+B` | 将任务转到后台 |
| `Esc` | 中断或退出 |
| `↑/↓` | 浏览历史命令 |
| `Tab` | 自动补全斜杠命令 |

---

# 第二部分：用户安装的 Skills

以下 Skills 安装在 `~/.claude/skills/` 目录，通过 `/skill-name` 方式调用。

---

## Superpowers 开发工作流系列

这是一套完整的软件开发工作流 Skills，来自 [Superpowers](https://github.com/superpowers) 项目。

### 核心入口

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `using-superpowers` | `/using-superpowers` | **核心入口** - 建立如何查找和使用 skills 的规范，要求在任何响应前先调用相关 skill |

### 规划与设计阶段

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `brainstorming` | `/brainstorming` | **创意设计** - 在任何创造性工作前必须使用，通过对话探索用户意图、需求和设计 |
| `writing-plans` | `/writing-plans` | **编写计划** - 为多步骤任务编写详细的实现计划，假设工程师对代码库零上下文 |
| `writing-skills` | `/writing-skills` | **编写 Skills** - 创建新 skills、编辑现有 skills，基于 TDD 方法验证 skill 效果 |
| `skill-creator` | `/skill-creator` | **Skill 创建器** - 创建、修改、优化 skills，运行评估测试和性能基准 |

### 实现阶段

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `executing-plans` | `/executing-plans` | **执行计划** - 加载实现计划，在独立会话中执行所有任务并设置审查检查点 |
| `subagent-driven-development` | `/subagent-driven-development` | **子代理驱动开发** - 每个任务分配独立子代理，执行后进行两阶段审查（规格审查+代码质量审查） |
| `dispatching-parallel-agents` | `/dispatching-parallel-agents` | **并行代理调度** - 面对 2+ 独立任务时，并行分配给专业代理处理 |
| `test-driven-development` | `/test-driven-development` | **测试驱动开发** - 先写测试，观察失败，再写最小代码通过测试 |

### 质量保障阶段

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `requesting-code-review` | `/requesting-code-review` | **请求代码审查** - 完成任务后调度代码审查子代理，在问题扩散前捕获 |
| `receiving-code-review` | `/receiving-code-review` | **接收代码审查** - 收到审查反馈后，要求技术严谨性和验证，而非盲目实现 |
| `verification-before-completion` | `/verification-before-completion` | **完成前验证** - 声称工作完成前必须运行验证命令并确认输出，证据先于断言 |
| `systematic-debugging` | `/systematic-debugging` | **系统化调试** - 遇到任何 bug 或测试失败时，必须先找到根本原因再尝试修复 |

### 分支与环境管理

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `using-git-worktrees` | `/using-git-worktrees` | **使用 Git Worktrees** - 为功能开发创建隔离工作空间，优先使用平台原生工具 |
| `finishing-a-development-branch` | `/finishing-a-development-branch` | **完成开发分支** - 实现完成后，引导选择 merge/PR/cleanup 等集成方式 |

---

## Nature 学术写作系列

这是一套专为学术写作和 Nature 系列期刊投稿设计的 Skills，支持中英文双语。

### 文献检索与管理

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `nature-academic-search` | `/nature-academic-search` | **学术文献检索** - 多源文献搜索、引文验证、MeSH 检索策略、引文文件管理 (.nbib/.ris/.bib 转换)，支持 PubMed/CrossRef/arXiv/Scopus/ScienceDirect |
| `nature-citation` | `/nature-citation` | **Nature 引用添加** - 为文稿添加严格的 Nature/CNS 引用，分段搜索旗舰期刊和子刊，导出 EndNote/RIS 格式 |

### 论文阅读与理解

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `nature-reader` | `/nature-reader` | **论文精读器** - 构建中英文对照、图表感知、来源锚定的 Markdown 论文阅读文档，支持 PDF/DOI/arXiv/HTML |

### 论文写作与润色

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `nature-writing` | `/nature-writing` | **Nature 风格写作** - 起草、重构或规划 Nature 风格的手稿章节（摘要、引言、方法、实验、讨论、结论等） |
| `nature-polishing` | `/nature-polishing` | **论文润色** - 润色、重构或翻译学术散文为 Nature 倾向的英文，支持 LaTeX 排版修复 |

### 图表与数据

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `nature-figure` | `/nature-figure` | **科研绘图** - 提交级 Nature/高影响力期刊图表工作流，支持 Python (matplotlib/seaborn) 和 R (ggplot2) |
| `nature-data` | `/nature-data` | **数据可用性声明** - 准备、审计或修订 Nature 级 Data Availability 声明、数据仓库计划、FAIR 元数据清单 |

### 审稿与回复

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `nature-reviewer` | `/nature-reviewer` | **模拟审稿人** - 模拟 Nature 风格的审稿人评估，返回 3 份审稿报告 + 交叉审查综合 |
| `nature-response` | `/nature-response` | **审稿意见回复** - 起草、审计或修订逐点审稿回复信，处理大修/小修意见 |

### 演示文稿

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `nature-paper2ppt` | `/nature-paper2ppt` | **论文转 PPT** - 从科学论文构建完整的 Nature 风格中文 PPTX 演示文稿，支持期刊汇报、组会、学术报告 |

---

## 开发工具类 Skills

### 代码与设计

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `frontend-design` | `/frontend-design` | **前端设计** - 创建独特的、生产级的前端界面，避免通用 AI 美学，支持各种风格（极简、复古未来、有机自然等） |
| `ui-ux-pro-max` | `/ui-ux-pro-max` | **UI/UX 设计智能** - 67 种风格、96 种调色板、57 种字体配对、25 种图表，支持 React/Vue/Svelte/SwiftUI/Flutter 等 13 种技术栈 |
| `karpathy-guidelines` | `/karpathy-guidelines` | **Karpathy 编码指南** - 减少常见 LLM 编码错误的行为准则，源自 Andrej Karpathy 的观察 |

### 文本处理

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `humanizer` | `/humanizer` | **文本去 AI 化** - 移除 AI 生成文本的痕迹，基于 Wikipedia 的 "AI 写作迹象" 指南，检测并修复夸张象征、促销语言、破折号过度使用等模式 |

### Skill 发现

| Skill | 调用命令 | 功能说明 |
|-------|----------|----------|
| `find-skills` | `/find-skills` | **查找 Skills** - 当用户问"如何做 X"或"有没有 X 的 skill"时，帮助发现和安装 agent skills |

---

## 环境变量配置

| 变量 | 说明 |
|------|------|
| `ANTHROPIC_API_KEY` | API 密钥 |
| `CLAUDE_CODE_ENABLE_AUTO_MODE` | 启用自动模式 (Bedrock/Vertex/Foundry) |
| `CLAUDE_CODE_SAFE_MODE` | 安全模式 (禁用所有自定义配置) |
| `CLAUDE_CODE_DISABLE_BUNDLED_SKILLS` | 禁用内置 skills |
| `CLAUDE_CODE_SESSION_ID` | 自定义会话 ID |
| `OTEL_LOG_TOOL_DETAILS` | 启用工具详细日志 |

---

## 使用提示

1. **查看所有可用命令**: 在会话中输入 `/` 然后按 `Tab` 查看自动补全列表
2. **Skills 自动加载**: `.claude/skills` 目录下的 skills 会自动加载
3. **热重载**: 使用 `/reload-skills` 可以在不重启会话的情况下重新加载 skills
4. **插件管理**: 使用 `/plugin` 浏览和安装来自 Marketplace 的插件
5. **Superpowers 工作流**: 建议从 `/using-superpowers` 开始，它会指导你使用正确的 skill
6. **Nature 学术系列**: 支持中英文双语，触发词包括"论文"、"润色"、"审稿"等

---

## 相关资源

- [Claude Code 官方文档](https://docs.anthropic.com)
- [Superpowers Skills](https://github.com/superpowers)
- [Plugin Marketplace](https://github.com/anthropics/claude-plugins-official)

---

*本文档基于 Claude Code v2.1.181 和用户已安装的 Skills 整理。*
